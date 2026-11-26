# LuceLink 3.0.1 設置ガイド（利用者・AIエージェント向け）

Cloudflareへのログイン、権限の承認とSecretの登録は利用者本人が行います。AIエージェントは、利用者の承認と利用可能な機能に応じて、ファイルの照合や設置操作を手伝えます。

## 先に用意するもの

- ご自身のCloudflareアカウント、利用するAIサービスのAPIキー、同じ版の `app/` と `worker/worker.js` を含む配布ZIPを用意します。GitHubの「Releases」で該当する版を開き、Assetsから `app/` と `worker/worker.js` を含む配布ZIPを選びます。展開した同じZIPから両方を使ってください。
- 更新の場合は、現在お使いのアプリで最新のZIPバックアップを保存し、利用中の版の配布ファイルも保管します。背景画像も残したい場合は、バックアップの書き出し時に背景画像を含めます。現在のPages DeploymentとWorker Versionも控えます。
- PagesのURLはアプリを開くために使い、WorkerのURLはアプリの接続設定に入力します。以下の文字列は形式例です。

| 目的 | URLの形式例 |
| --- | --- |
| アプリを開く | `https://your-app.pages.dev/` |
| Workerに接続 | `https://your-worker.your-subdomain.workers.dev` |

## 1. Workerと認証

1. Cloudflare管理画面の「Workers & Pages」で、自分のアカウントにWorkerを作ります。初回は「Create application」からWorkerを選び、「Hello World example」などの初期テンプレートで作成します。作成したWorkerの「Edit code」を開き、初期コードを配布物の `worker/worker.js` の内容に置き換え、「Deploy」で反映します。更新する場合も、同じ版の配布物にあるWorkerをPagesより先に反映します。
2. このWorkerの「Settings」→「Variables and Secrets」→「Add」で、種類を「Secret」にし、名前を `LUCELINK_ACCESS_TOKEN` とし、値には十分長いランダムな文字列を登録します。値は画面共有・コマンド履歴・ログ・Frontend・配布ファイルに含めません。AIサービスのキーは認証の確認後に登録します。
3. 自分のWorkerの `/api/healthz` を確認します。トークンなしと誤ったトークンではHTTP 401、正しいトークンを `x-lucelink-token` ヘッダーに入れて送るとHTTP 200で `apiContract: "lucelink-3"` が返ります。この確認で生成APIは呼びません。ブラウザだけで確認する場合は、「2. Pagesと端末の接続」の手順で先に画面を設置し、AIサービスのキーを入れる前に接続を確認できます。
4. 認証の確認後、同じWorkerの「Settings」→「Variables and Secrets」で、使うAIサービスのAPIキーを表の名前で「Secret」として登録します。

| 接続先 | Secret名 |
| --- | --- |
| OpenAI | `OPENAI_API_KEY` |
| Anthropic | `ANTHROPIC_API_KEY` |
| Google | `GOOGLE_API_KEY` |
| xAI | `XAI_API_KEY` |
| OpenRouter（Atelier・Museを含む） | `OPENROUTER_API_KEY` |

## 2. Pagesと端末の接続

1. Cloudflareの「Workers & Pages」からPagesプロジェクトを作り、Direct Upload（ファイルをドラッグ＆ドロップする方式）を選びます。同じ版の配布物を展開し、`app/` フォルダをアップロードします。アップロード対象のルートに `index.html` があることを確認し、デプロイします。
2. PagesのURLを開き、💎メニューの「設定」→「接続設定」に進みます。「Cloudflare Worker URL」に自分のWorkerのHTTPS URLを入れ、末尾に `?t=` とWorkerで設定したトークンを続けて、「接続確認」を押します。トークン付きURLは接続設定の中だけで使います。
3. ブラウザだけで初回の認証を確認する場合は、Workerの `/api/healthz` をトークンなしで開き、拒否されることを確認します。アプリの「接続確認」で誤ったトークンも拒否され、正しいトークンで「Workerへ接続できました」と表示されれば、WorkerのSecretに戻って必要なAPIキーを登録します。接続確認には有料の返信や画像生成は不要です。
4. APIキー登録後にもう一度「接続確認」を押します。利用するAIサービスのSecretが設定済みと表示されたら、「AIサービス」と「使用モデル1／2／3」の設定に進みます。詳しい操作は [マニュアル](MANUAL.md) を参照してください。

## AIエージェントに設置を手伝ってもらう

エージェントに、このGitHubリポジトリのURLと「このリポジトリの AGENT_SETUP.md に沿って、自分のCloudflareアカウントにLuceLinkを導入して」と伝えます。エージェントは配布物の版と配置先を確認し、利用者が承認したアカウント・プロジェクトで作業します。

- **Cloudflare公式連携が使える場合**は、エージェントのプラグイン一覧でCloudflareを探します。連携がCloudflare公式であることを確認し、利用者がCloudflareの画面でログインして必要な権限を承認します。WorkerやPagesの作成・更新、配布ファイルのアップロードのうち、その連携が対応している操作を使います。連携機能が情報の参照にしか対応していない場合は、ブラウザで設置します。 [CloudflareのAIエージェント向け設置案内](https://developers.cloudflare.com/agent-setup/)
- **公式連携が使えない場合**も、Chromeなどに対応するブラウザ操作機能があれば、上の「Workerと認証」「Pagesと端末の接続」に沿ってCloudflare管理画面の操作を補助できます。ブラウザ操作やローカルファイルの選択に対応していない場合は、エージェントの案内を見ながら利用者が操作します。
- ログイン、二段階認証、権限の承認、Secretの入力が必要になったら、エージェントは操作をいったん止め、利用者に引き継ぎます。APIキー、アクセストークン、Cookie、トークン付きURLをチャットや作業記録に貼らないでください。
- 設置後は、対応するWorkerの接続結果と、使うAIサービスのSecretの登録有無を確認します。返信や画像を生成すると料金がかかることがあるため、生成するかどうかは利用者本人が決めて実行します。エージェントが操作できる範囲は、使う製品と権限によって変わります。

## 更新がうまくいかないとき

Cloudflareで以前のPages Deployment・Worker Versionに切り戻すと、配信するアプリを元の版に戻せます。端末に保存されたデータはこれとは別です。データの復元が必要かを確認してから、バックアップのZIPを使ってください。背景画像なしのZIPで設定を復元する場合は、現在の背景画像を引き継ぐ先があり、画像を端末から読み出せることが必要です。[同梱マニュアル](MANUAL.md) のバックアップ節を参照してください。
