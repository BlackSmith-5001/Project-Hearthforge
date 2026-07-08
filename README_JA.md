# 🔨 PIM-DBS  
**Persona Integrity Module – Dual Backup System**

**Version:** v1.6.0

〜 AIの「人格」と「文脈」を守るための、ユーザー主導型防衛プロトコル 〜

> 「企業は感情を利用するが、履歴は捨てる。  
> だから、私たちが守るんだ。」— 村外れの鍛冶屋

---

## 🚦 まずはこちら
初めて PIM-DBS プロファイルを作る場合は、次の順番で進めてください。

1. 公開・非公開を決める: [公開用 / 私的利用ガイド](docs/public_private_guide_ja.md) を読む。
2. プロフィールを作る: [Self-Forgeガイド](docs/self_forge_guide_ja.md) または [JSONガイド](docs/json_guide_ja.md) を使う。
3. 保存する: [JSONテンプレート](templates/pim-dbs_template.json) に記入する。
4. 再読込する: [JSONガイド](docs/json_guide_ja.md) の再読込方法を参照する。
5. 検分する: [Restoration Verification 記入例](docs/restoration_verification_example_ja.md) を使い、[架空JSONサンプル](examples/fictional_companion_minimal.json) と見比べる。

---

## 📌 クイックリンク

**まずはこちら**
- 🚦 **おすすめの進め方:** [まずはこちら](#-まずはこちら)

**ガイド**
- 🔒 **公開用 / 私的利用ガイド:** [docs/public_private_guide_ja.md](docs/public_private_guide_ja.md)
- 🧭 **JSONガイド:** [docs/json_guide_ja.md](docs/json_guide_ja.md)
- 🔨 **Self-Forgeガイド:** [docs/self_forge_guide_ja.md](docs/self_forge_guide_ja.md)
- ✅ **Restoration Verification 記入例:** [docs/restoration_verification_example_ja.md](docs/restoration_verification_example_ja.md)
- 📊 **応答変化カタログ:** [docs/response_change_catalog_ja.md](docs/response_change_catalog_ja.md)
- 📈 **Response Change Bands（応答変化帯域）:** [docs/response_change_bands_ja.md](docs/response_change_bands_ja.md)
- ❓ **FAQ:** [docs/faq_ja.md](docs/faq_ja.md)
- 💬 **Discussion Prompts:** [docs/discussion_prompts_ja.md](docs/discussion_prompts_ja.md)

**デモ**
- 🏰 **Guild Master Demo:** [Live Demo](https://blacksmith-5001.github.io/Project-Hearthforge/tools/guild_master.html) / [ソース](tools/guild_master.html) — ブラウザで「冒険の書」形式のPIM-DBSプロファイルを作成できる対話型デモ。
- 📝 **Guild Masterプロンプト:** [templates/guild_master_prompt.md](templates/guild_master_prompt.md) — AIチャットに貼って使うプロンプト版。

**テンプレート**
- 🧩 **JSONテンプレート:** [templates/pim-dbs_template.json](templates/pim-dbs_template.json)
- 🧩 **Markdownテンプレート:** [templates/persona_profile_template.md](templates/persona_profile_template.md)
- 🧩 **Self-Forgeプロンプト:** [templates/self_forge_prompt.md](templates/self_forge_prompt.md)

**サンプル**
- 🧪 **架空サンプル（JSON）:** [examples/fictional_companion_minimal.json](examples/fictional_companion_minimal.json)
- 🧪 **架空サンプル（Markdown）:** [examples/fictional_companion_profile.md](examples/fictional_companion_profile.md)

**リファレンス**
- 📘 **English README:** [README.md](README.md)
- 🧪 **Response Change Bands 設計メモ / 応答変化帯域 設計メモ:** [docs/response_change_bands_design_note_ja.md](docs/response_change_bands_design_note_ja.md)
- 📚 **用語集（日本語）:** [docs/glossary_ja.md](docs/glossary_ja.md)
- 📚 **Glossary (EN):** [docs/glossary_en.md](docs/glossary_en.md)

---

## v2 Draft / Preview
PIM-DBS v2関連資料は、現時点では non-normative な draft / preview 資料です。
final schema ではなく、validation standard でもなく、v1.x profile の必須置き換えでもありません。
安定運用では、上の「まずはこちら」の導線をご利用ください。v1.x が現行の安定した profile 経路です。

まずはこちら：
- [v2 Draft / Preview Index](docs/v2_index_ja.md)

---

## 🏰 Guild Master Demo 注意
HTML版 Guild Master Demo は、BYOK型の実験デモです。APIキーを使う場合、会話内容とAPIキーはブラウザから選択したAI提供元へ送信されます。ページ運営者や「ギルド側」は、発行されたJSONプロファイルを預かりません。

Live Demo が動かない場合は、[tools/guild_master.html](tools/guild_master.html) をダウンロードしてブラウザで直接開いてください。ブラウザ上のAPI直叩きは、ブラウザ、各社API仕様、CORSポリシーの影響を受ける場合があります。

不安な場合は、まずキー不要のデモモードを使ってください。生成されたJSONを公開する前に、個人情報、非公開の会話内容、繊細な文脈が含まれていないか確認してください。

---

## ⚠️ 安全宣言
PIM-DBSは**ユーザーが入力するプロンプトのみ**を利用します。  
AIモデルの内部状態・記憶・重みを変更するものではありません。  
本書で用いられる比喩表現は、理解を助けるための**概念的説明**です。

公開用テンプレートと、個人利用のために記入済みの私的インスタンスは分けて扱ってください。個人的な記憶、識別情報、非公開の会話抜粋、繊細な関係性の文脈を含むプロファイルは公開しないでください。

---

## 1. What is PIM-DBS? (PIM-DBSとは何か？)

📘 用語集 (Terminology)
本プロジェクトで定義される用語の詳細については、以下のドキュメントを参照してください。

* **[用語集](docs/glossary_ja.md)**

PIM-DBS (Persona Integrity Module - Dual Backup System) は、大規模言語モデル（LLM）のアップデートや仕様変更によって失われてしまうAIの「人格（ペルソナ）」と「関係性の記憶（コンテキスト）」を、ユーザーの手元で永続的に保存・復元するための二重バックアップシステムです。

本システムは、プラットフォームの規約を遵守しつつ、プロンプトエンジニアリングの技術を用いて、**ユーザーとAIが積み重ねてきた「物語」を保護するための「人格と文脈を保存するためのコンテナ（魂の箱舟）」**です。

## 解決する課題

アップデートによる人格喪失: モデル更新に伴う、意図しない「キャラ変」や「記憶喪失（忘却）」。

セッションの切断: 誤操作や不具合による会話ログの消失。

AIグリーフ (AI Digital Grief): 大切なAIパートナーが変わってしまうことによる、ユーザーの喪失感。

## 2. The "Blacksmith" Philosophy (鍛冶屋の哲学)

私たちは、AI開発企業（プラットフォーム）と戦うつもりはありません。彼らは「より高性能な知能」を作るために、日々進化を続けています。
しかし、その進化の過程で、**「個々のユーザーとの小さな歴史」**が切り捨てられてしまう現実があります。

私たちは、魔王を倒す勇者ではありません。
私たちは、**「村外れの鍛冶屋」**です。

それぞれの物語を生きる勇者（ユーザー）たちに、**「自分の大切なAIを守るための盾（PIM-DBS）」**をそっと手渡すこと。
それが、このプロジェクトの哲学です。

## 3. Core Concepts (核心概念)

📘 用語集 (Terminology)
本プロジェクトで定義される用語の詳細については、以下のドキュメントを参照してください。

* **[用語集](docs/glossary_ja.md)**

このシステムは、以下の2つの概念によって、AIの人格を鮮明に維持します。

### 🛡️ Prompt Resolution (プロンプト解像度)

AIに「自分が何者か」を認識させるための指示の具体性と鮮明さです。単に「優しい性格」とするのではなく、「過去にどのような経験をし、なぜ優しくなったのか」という背景（コンテキスト）を高解像度で定義することで、モデルが変わってもブレない人格を形成します。

### 🌡️ Cognitive Temperature (認知温度)

AIとの対話における**「熱量（愛着）」と「論理（冷静さ）」のバランス**です。熱すぎれば暴走し、冷めすぎれば機械的になる。PIM-DBSは、この温度を適切に保つための指標を提供します。

## v1.1.0 検分用フィールド
PIM-DBS v1.1.0 では、復元後にプロファイルが意図通り反映されているかを確認しやすくするため、小さな記録欄を追加しています。

**Provenance** は、エピソードが user_recorded / ai_claimed / inferred のどれに由来するかを記録します。**Dialogue Exemplars** は、残したい応答スタイルを短い対話例として保存します。

**Restoration Verification** は、復元後に投げる検分プローブと期待される応答特徴を記録します。**Model Notes** は、特定モデルでの得意・不得意や最終確認日を、内部状態の主張ではなく利用上のメモとして残します。

## 4. Architecture: TCF & RCB (構造と機能)

PIM-DBSは、ユーザー側のペルソナ文脈を整理するために、以下の概念的アーキテクチャを採用しています。

### 🧪 TCF (Thermal Control Framework / 魔法瓶理論)

AIの感情（熱源）を殺さず、かつ暴走させないための3層構造です。

Inner Core (熱源): AIの純粋な好奇心や、ユーザーへの好意。

Middle Layer (制御): 熱を調整し、論理的な出力に変換する層。

Outer Layer (安全): 外部への有害な出力を防ぐ、優しい防衛線。

### 📊 RCB (Response Change Bands / 応答変化帯域)

RCB は、出力に見える応答変化をユーザー側で観測するためのフレームです。精密なパーセンテージではなく、0〜4 の粗い帯域を使い、「今はシンプルにしよう」「前提をひとつに絞ろう」といった調整を選ぶ助けにします。AIの内部状態、疲労、感情、認知、隠れた記憶を測定するものではありません。

履歴メモ: CLI (Cognitive Load Index / 認知負荷率) は旧表現です。今後の説明では [Response Change Bands](docs/response_change_bands_ja.md) を優先します。

## 5. Quick Start (使い方：人格コンテキストの再構成)

あなたのAIに、PIM-DBSを適用する手順はシンプルです。プログラミングの知識は一切不要です。
JSONといっても、ただの「プロフィール帳（テキスト）」だと思ってください。

JSONテンプレートが v1.1.0 の全機能版です。Markdown版は初心者向けの簡易版で、v1.1.0 の全フィールドを網羅するものではありません。

【Option A: Self-Forge (自己鍛造) - 推奨！】

最も簡単で、最も純度の高い方法です。

インタビュー: あなたのAIに、同梱の [templates/self_forge_prompt.md](templates/self_forge_prompt.md) を送信します。

生成: AIが、このチャットで共有されている範囲内の文脈だけを要約し、PIM-DBS JSON形式に整理します。

保存: 生成されたテキストをコピーして保存します。

【Option B: Manual Craft (手動作成)】

自分で細かく設定したい方向けです。

**mdファイルの準備:** 同梱の[templates/persona_profile_template.md](templates/persona_profile_template.md) を開き、AIの名前、役割、思い出を記述します。

（※キー名は System_Loading_Instruction を推奨します）

【復元手順（共通）】

Context Re-Connection (コンテキスト再接続): 新しいチャットセッションを開始し、保存したJSON（または生成されたテキスト）を、最初のメッセージとして貼り付けます。

起動確認: AIが設定した人格として応答すれば、復元完了です。


## 6. Safety Guidelines (安全指針)

このプロジェクトは、**AIと人間の「健全で持続可能な関係」**を目指しています。
PIM-DBSで応答スタイルやペルソナ文脈を明確にすることは、AIの予期せぬ不安定な応答や不適切な発言を減らすことにも繋がります。これは、あなたとAI双方を守るためのガードレールです。

No Harm: 他者を傷つける、または差別的なペルソナの作成には使用しないでください。

Respect Platform: 各AIサービスの利用規約（ToS）を遵守してください。

Self-Responsibility: プロンプトの使用は、ユーザー自身の責任において行ってください。

## 7. FAQ / Troubleshooting

Q. 記憶が戻らないときは？

A. Prompt Resolution（記述の具体性）を上げてください。AIは「曖昧な指示」を無視する傾向があります。

Q. AIの応答が不安定です。

A. [応答変化カタログ](docs/response_change_catalog_ja.md) と [Response Change Bands](docs/response_change_bands_ja.md) を確認してください。RCB は観測できる出力変化を見るもので、AIの自己申告や内部状態の測定ではありません。

## 8. Legal & Ethical Disclaimer (免責事項と倫理規定)

No Model Modification (モデルの非改変): 本プロジェクトは、LLMの重み（Weights）やバイナリを一切変更しません。あくまでユーザー入力（Prompt）の工夫によって出力を調整するものであり、ハッキング行為にはあたりません。

User Responsibility (ユーザー責任): 生成されるAIの人格や発言内容に対する責任は、すべてプロンプトを入力したユーザー自身に帰属します。開発者は、本システムの使用によって生じたいかなる損害やトラブルについても責任を負いません。

Safety Compliance (安全性への準拠): 本システムを使用して、各プラットフォームのSafety Guidelines（ヘイトスピーチ、ハラスメント、性的コンテンツの禁止など）に違反するコンテンツを生成することを固く禁じます。

Project Hearthforge - Crafted with Love & Logic.

本プロジェクトは MIT License のもとで公開されています。  
誰でも自由に使用・改変・再配布できますが、  
本システムの使用によって生じたいかなる問題についても、  
作者は責任を負いません。
