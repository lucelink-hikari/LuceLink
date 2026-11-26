# LuceLink 3.0.1 モデル一覧

2026年11月22日のモデル一覧を基に、11月26日のメンテナンス差分を反映しています。ご自身のアカウントで利用できるモデルは、各AIサービスに接続したときの一覧で確認してください。

| 接続先 | アプリに定義されたID・系列 | 通常欄の候補 | 一覧を取得できないときの代替候補（うち通常欄） |
| --- | --- | --- | --- |
| OpenAI公式 | 20 | 11 | 20（11） |
| Anthropic公式 | 15 | 7 | 15（7） |
| Google公式 | 15 | 10 | 15（10） |
| xAI公式 | 5 | 4 | 5（4） |
| OpenRouter | 67 | 32 | 23（23） |

コードに記載された接続先とモデルID・系列の組み合わせ、**計122件**を掲載します。内訳は代替定義78件、代替定義のない通常・Worker候補9件、通常・代替候補に含まれない並び順の定義17件、上限表だけの定義18件です。同じモデルも公式APIとOpenRouterで別に数えます。対象はUI・Workerの候補表と並び順、および出力上限表です。提供元から動的に取得する全モデルの件数は未確認です。

## 表の読み方

- **通常欄**はアプリ画面に通常表示する候補、**Worker**はWorkerが通常取得する候補です。両方で候補となっていても、提供元の一覧・フィルター・シリーズの重複整理により表示は変わります。APIの返却IDが日付付きの場合は、該当系列として扱われる場合があります。
- **代替**は、サービスから一覧を取得できず、保存済みの一覧も利用できない場合に使う候補です。通常欄では通常候補の条件も適用されます。**並び順**と**上限表のみ**は候補としての表示や提供を保証しません。
- **送信上限**はLuceLinkがリクエストに使用する上限です。上限表に一致しないIDには6,000を使用します。この表はソースコードとの照合に基づくものです。サービスの最大出力、料金、コンテキスト長を実際の通信で測定したものではありません。

## OpenAI公式

| API ID・系列 | 代替表示名 | 選択・取得での扱い | 送信上限 |
| --- | --- | --- | --- |
| `gpt-6-astra` | GPT-6 Astra | 通常欄／Worker／代替 | 128,000 |
| `gpt-6.2-astra` | GPT-6.2 Astra | 通常欄／Worker／代替 | 128,000 |
| `gpt-6.2-sol` | GPT-6.2 Sol | 通常欄／Worker／代替 | 128,000 |
| `chat-latest` | ChatGPT Latest | 通常欄／Worker／代替 | 128,000 |
| `gpt-6.1-sol` | GPT-6.1 Sol | 通常欄／Worker／代替 | 128,000 |
| `gpt-6.1-terra` | GPT-6.1 Terra | 通常欄／Worker／代替 | 128,000 |
| `gpt-6-sol` | GPT-6 Sol | 通常欄／Worker／代替 | 128,000 |
| `gpt-6-luna` | GPT-6 Luna | 通常欄／Worker／代替 | 128,000 |
| `gpt-5.6-sol` | GPT-5.6 Sol | 通常欄／Worker／代替 | 128,000 |
| `gpt-5.6-terra` | GPT-5.6 Terra | 通常欄／Worker／代替 | 128,000 |
| `gpt-5.6-luna` | GPT-5.6 Luna | 通常欄／Worker／代替 | 128,000 |
| `gpt-5.1` | GPT-5.1 | Worker／代替 | 128,000 |
| `gpt-5` | GPT-5 | Worker／代替 | 128,000 |
| `gpt-5-pro` | GPT-5 Pro | 代替 | 272,000 |
| `gpt-5-mini` | GPT-5 Mini | 代替 | 128,000 |
| `gpt-5-nano` | GPT-5 Nano | 代替 | 128,000 |
| `gpt-4.1` | GPT-4.1 | 代替 | 32,768 |
| `gpt-4.1-mini` | GPT-4.1 Mini | 代替 | 32,768 |
| `gpt-4o` | GPT-4o | 代替 | 16,384 |
| `gpt-4o-mini` | GPT-4o Mini | 代替 | 16,384 |

## Anthropic公式

| API ID・系列 | 代替表示名 | 選択・取得での扱い | 送信上限 |
| --- | --- | --- | --- |
| `claude-fable-5-2` | Claude Fable 5.2 | 通常欄／Worker／代替 | 128,000 |
| `claude-fable-5-1` | Claude Fable 5.1 | 通常欄／Worker／代替 | 128,000 |
| `claude-opus-5-5` | Claude Opus 5.5 | 通常欄／Worker／代替 | 128,000 |
| `claude-sonnet-5-5` | Claude Sonnet 5.5 | 通常欄／Worker／代替 | 128,000 |
| `claude-sonnet-5` | Claude Sonnet 5 | 通常欄／Worker／代替 | 128,000 |
| `claude-haiku-5-5` | Claude Haiku 5.5 | 通常欄／Worker／代替 | 128,000 |
| `claude-haiku-4-5` | Claude Haiku 4.5 | 通常欄／Worker／代替 | 64,000 |
| `claude-opus-5` | Claude Opus 5 | Worker／代替 | 128,000 |
| `claude-opus-4-8` | Claude Opus 4.8 | Worker／代替 | 128,000 |
| `claude-opus-4-7` | Claude Opus 4.7 | Worker／代替 | 128,000 |
| `claude-sonnet-4-6` | Claude Sonnet 4.6 | Worker／代替 | 128,000 |
| `claude-opus-4-6` | Claude Opus 4.6 | Worker／代替 | 128,000 |
| `claude-fable-5` | Claude Fable 5 | 代替 | 128,000 |
| `claude-sonnet-4-5` | Claude Sonnet 4.5 | 代替 | 64,000 |
| `claude-opus-4-5` | Claude Opus 4.5 | 代替 | 64,000 |

## Google公式

| API ID・系列 | 代替表示名 | 選択・取得での扱い | 送信上限 |
| --- | --- | --- | --- |
| `gemini-4-argon` | Gemini 4 Argon | 通常欄／Worker／代替 | 65,536 |
| `gemini-4-carbon` | Gemini 4 Carbon | 通常欄／Worker／代替 | 65,536 |
| `gemini-4-neon` | Gemini 4 Neon | 通常欄／Worker／代替 | 65,536 |
| `gemini-4-hydrogen` | Gemini 4 Hydrogen | 通常欄／Worker／代替 | 65,536 |
| `gemini-3.8-flash` | Gemini 3.8 Flash | 通常欄／Worker／代替 | 65,536 |
| `gemini-3.7-flash` | Gemini 3.7 Flash | 通常欄／Worker／代替 | 65,536 |
| `gemini-3.6-flash` | Gemini 3.6 Flash | 通常欄／Worker／代替 | 65,536 |
| `gemini-3.5-flash` | Gemini 3.5 Flash | 通常欄／Worker／代替 | 65,536 |
| `gemini-3.5-flash-lite` | Gemini 3.5 Flash Lite | 通常欄／Worker／代替 | 65,536 |
| `gemini-3.1-flash-lite` | Gemini 3.1 Flash Lite | 通常欄／Worker／代替 | 65,536 |
| `gemini-3.1-pro-preview` | Gemini 3.1 Pro Preview | 代替 | 65,536 |
| `gemini-3-flash-preview` | Gemini 3 Flash Preview | 代替 | 65,536 |
| `gemini-2.5-pro` | Gemini 2.5 Pro | 代替 | 65,536 |
| `gemini-2.5-flash` | Gemini 2.5 Flash | 代替 | 65,536 |
| `gemini-2.5-flash-lite` | Gemini 2.5 Flash Lite | 代替 | 65,536 |

## xAI公式

| API ID・系列 | 代替表示名 | 選択・取得での扱い | 送信上限 |
| --- | --- | --- | --- |
| `grok-4.7` | Grok 4.7 | 通常欄／Worker／代替 | 6,000（既定上限） |
| `grok-4.6` | Grok 4.6 | 通常欄／Worker／代替 | 6,000（既定上限） |
| `grok-4.5` | Grok 4.5 | 通常欄／Worker／代替 | 6,000（既定上限） |
| `grok-4.3` | Grok 4.3 | 通常欄／Worker／代替 | 6,000（既定上限） |
| `grok-4.20` | Grok 4.20 | 代替 | 6,000（既定上限） |

## OpenRouter

| API ID・系列 | 代替表示名 | 選択・取得での扱い | 送信上限 |
| --- | --- | --- | --- |
| `openrouter/free` | Free Models Router（提供状況を確認） | 通常欄／Worker／代替 | 6,000（既定上限） |
| `openai/gpt-6-astra` | GPT-6 Astra | 通常欄／Worker／代替 | 128,000 |
| `openai/gpt-6.2-astra` | GPT-6.2 Astra | 通常欄／Worker／代替 | 128,000 |
| `openai/gpt-6.2-sol` | GPT-6.2 Sol | 通常欄／Worker／代替 | 128,000 |
| `openai/gpt-chat-latest` | ChatGPT Latest | 通常欄／Worker／代替 | 128,000 |
| `openai/gpt-6.1-sol` | GPT-6.1 Sol | 通常欄／Worker／代替 | 128,000 |
| `openai/gpt-6.1-terra` | GPT-6.1 Terra | 通常欄／Worker／代替 | 128,000 |
| `openai/gpt-6-sol` | GPT-6 Sol | 通常欄／Worker／代替 | 128,000 |
| `openai/gpt-6-luna` | GPT-6 Luna | 通常欄／Worker／代替 | 128,000 |
| `openai/gpt-5.6-terra` | — | 通常欄／Worker | 128,000 |
| `openai/gpt-5.6-sol` | — | 通常欄／Worker | 128,000 |
| `openai/gpt-5.6-luna` | — | 通常欄／Worker | 128,000 |
| `anthropic/claude-sonnet-5` | Claude Sonnet 5 | 通常欄／Worker／代替 | 128,000 |
| `anthropic/claude-sonnet-5.5` | Claude Sonnet 5.5 | 通常欄／Worker／代替 | 128,000 |
| `anthropic/claude-fable-5.2` | Claude Fable 5.2 | 通常欄／Worker／代替 | 128,000 |
| `anthropic/claude-fable-5.1` | Claude Fable 5.1 | 通常欄／Worker／代替 | 128,000 |
| `anthropic/claude-opus-5.5` | Claude Opus 5.5 | 通常欄／Worker／代替 | 128,000 |
| `anthropic/claude-opus-5` | — | 通常欄／Worker | 128,000 |
| `anthropic/claude-haiku-5.5` | Claude Haiku 5.5 | 通常欄／Worker／代替 | 128,000 |
| `anthropic/claude-haiku-4.5` | Claude Haiku 4.5 | 通常欄／Worker／代替 | 64,000 |
| `google/gemini-4-argon` | Gemini 4 Argon | 通常欄／Worker／代替 | 65,536 |
| `google/gemini-4-carbon` | Gemini 4 Carbon | 通常欄／Worker／代替 | 32,768 |
| `google/gemini-4-neon` | Gemini 4 Neon | 通常欄／Worker／代替 | 65,536 |
| `google/gemini-4-hydrogen` | Gemini 4 Hydrogen | 通常欄／Worker／代替 | 65,536 |
| `google/gemini-3.8-flash` | Gemini 3.8 Flash | 通常欄／Worker／代替 | 65,536 |
| `google/gemini-3.6-flash` | — | 通常欄／Worker | 65,536 |
| `google/gemini-3.5-flash` | — | 通常欄／Worker | 65,536 |
| `google/gemini-3.5-flash-lite` | Gemini 3.5 Flash Lite | 通常欄／Worker／代替 | 65,536 |
| `x-ai/grok-4.6` | — | 通常欄／Worker | 450,000 |
| `x-ai/grok-4.7` | Grok 4.7 | 通常欄／Worker／代替 | 450,000 |
| `x-ai/grok-4.5` | — | 通常欄／Worker | 450,000 |
| `sakana/sakana-namazu` | — | 通常欄／Worker | 65,536 |
| `openai/gpt-5.1` | — | 並び順 | 128,000 |
| `openai/gpt-5` | — | 並び順 | 128,000 |
| `anthropic/claude-fable-5` | — | 並び順 | 128,000 |
| `anthropic/claude-opus-5-fast` | — | 並び順 | 6,000（既定上限） |
| `anthropic/claude-opus-4.8` | — | 並び順 | 128,000 |
| `anthropic/claude-opus-4.7` | — | 並び順 | 128,000 |
| `anthropic/claude-sonnet-4.6` | — | 並び順 | 128,000 |
| `anthropic/claude-opus-4.6` | — | 並び順 | 128,000 |
| `google/gemini-3.1-flash-lite` | — | 並び順 | 65,536 |
| `google/gemini-3.1-pro-preview` | — | 並び順 | 65,536 |
| `google/gemini-3-flash-preview` | — | 並び順 | 65,536 |
| `google/gemini-2.5-pro` | — | 並び順 | 65,536 |
| `google/gemini-2.5-flash` | — | 並び順 | 65,535 |
| `google/gemini-2.5-flash-lite` | — | 並び順 | 65,535 |
| `x-ai/grok-4.3` | — | 並び順 | 6,000（既定上限） |
| `x-ai/grok-4.20` | — | 並び順 | 6,000（既定上限） |
| `sakana/fugu-ultra` | — | 並び順 | 6,000（既定上限） |
| `openai/gpt-6.1-sol-pro` | — | 上限表のみ | 128,000 |
| `openai/gpt-6.1-terra-pro` | — | 上限表のみ | 128,000 |
| `openai/gpt-5-pro` | — | 上限表のみ | 128,000 |
| `openai/gpt-5-mini` | — | 上限表のみ | 128,000 |
| `openai/gpt-5-nano` | — | 上限表のみ | 128,000 |
| `openai/gpt-4.1` | — | 上限表のみ | 32,768 |
| `openai/gpt-4.1-mini` | — | 上限表のみ | 32,768 |
| `openai/gpt-4o` | — | 上限表のみ | 16,384 |
| `openai/gpt-4o-mini` | — | 上限表のみ | 16,384 |
| `anthropic/claude-sonnet-4.5` | — | 上限表のみ | 64,000 |
| `anthropic/claude-opus-4.5` | — | 上限表のみ | 64,000 |
| `google/gemini-3.7-flash` | — | 上限表のみ | 65,536 |
| `meta/muse-spark-1.3` | — | 上限表のみ | 131,072 |
| `meta/muse-ember` | — | 上限表のみ | 524,288 |
| `meta/muse-spark-1.2` | — | 上限表のみ | 16,000 |
| `meta/muse-spark-1.1` | — | 上限表のみ | 16,000 |
| `meta/muse-wonder` | — | 上限表のみ | 16,000 |
| `meta/muse-spark-open` | — | 上限表のみ | 131,072 |

## 2026年11月26日の提供状況

- OpenAI公式のGPT-4.1 nanoは提供終了。OpenRouterでは公開カタログに掲載されています。公式のGPT-5／mini／nano／proは12月11日、GPT-5.1は2027年4月1日に終了予定です。OpenRouterのGPT-5／mini／nano／proにも12月11日の終了予定が掲載されています。
- Anthropic公式のSonnet 4.5は11月30日、Opus 4.5は2027年1月22日に終了予定。Haiku 4.5は提供中です。OpenRouterでは3モデルとも掲載されており、公開カタログに終了日は掲載されていません。
- Google公式のGemini 2.5 Pro／Flashは既存の利用条件付きで、12月1日からそれぞれGemini 3.8 Flash／3.5 Flash-Liteへ自動転送予定です。OpenRouterは両モデルに12月1日の掲載終了日を表示しています。Flash-Liteは両経路で掲載継続中です。
- xAI公式の旧Grok 3／4／4.1 Fastの対象IDはGrok 4.3へ自動転送されるため、従来モデルとしての候補から外しています。OpenRouterの公開一覧では同じ旧モデルの掲載を確認できませんでした。

参照先は [OpenAI](https://developers.openai.com/api/docs/deprecations)、[Anthropic](https://platform.claude.com/docs/en/about-claude/model-deprecations)、[Google](https://ai.google.dev/gemini-api/docs/deprecations)、[xAI](https://docs.x.ai/developers/migration/may-15-retirement)、[OpenRouter公開カタログ](https://openrouter.ai/api/v1/models) です。

## 通常チャットの画像入力・Temperature

- ChatGPT Latestは両経路で画像入力に対応し、出力上限は128,000トークンです。OpenAI公式ではTemperatureを指定せず、OpenRouterでは対応パラメーターに沿って扱います。確認時のOpenRouterカタログにTemperatureは含まれていません。
- 画像入力は公式APIごとのモデル判定と取得結果で決まります。Google直結ではGemini 4 Argon・Carbon・HydrogenをJPEG入力の対象にしています。OpenRouterは取得した `input_modalities` の `image` を参照し、Carbon・Hydrogen・Haiku 5.5の代替候補にも画像対応を指定しています。実通信は未確認です。
- Temperatureを送らない条件は、OpenAIの一部のGPT-6系・GPT-5系・o系、AnthropicのFable・Mythos・Sonnet 5・Opus 4.7以降・Haiku 5.5に相当するコード上の条件、GoogleのGemini 3系／4 Argon・Carbon・Hydrogenです。OpenRouter版のCarbon・Hydrogen・Haiku 5.5もTemperatureを送信しません。他のOpenRouter候補は対応パラメータを参照します。
- Meta Museの設定値はOpenRouterの出力上限表にあります。Museの直接API接続や通常欄・代替候補はありません。Spark 1.1／1.2とWonderの16,000はLuceLinkの暫定値です。Ember、Sparkの各経路も提供・実効上限・プライバシー条件は未確認です。
- スライダーは、モデルの送信上限と16,000のうち、小さいほうの値まで調整できます。それより大きな値を設定するときは、数値を直接入力します。943,718は既存設定の保持上限で、APIの出力上限ではありません。保存した設定値は変えず、送信する値だけを上限に収めます。

## Atelierの画像生成モデル

画像生成モデルはOpenRouterの画像用カタログから `/api/atelier/models` で取得します。固定モデル一覧・代替候補の定義はありません。画像出力に対応し、SVG専用ではない候補を対象にします。参考画像の条件は取得情報から判定し、現行画面で扱う参考画像は最大1枚です。2枚以上が必須のモデルは候補から外します。通常チャットの画像入力とは別機能です。現在の全モデル、価格、参考画像付き生成は未確認です。

## 確認元

Frontend `LuceLinkBase.tsx`、`outputBudget.ts`、`outputBudgetSlider.ts`、Worker `src/index.ts`、`src/modelParameters.ts`、`src/outputBudget.ts`、`src/atelier.ts`。配布前の確認事項は、開発側の照合記録を参照してください。
