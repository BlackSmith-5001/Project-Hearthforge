# PIM-DBS v2.0 Public Example Design Note

この文書は、非規範的な設計メモです。PIM-DBS v2.0候補構造において、公開して安全なサンプルをどう設計するかを検討するためのものです。

これは確定した v2.0 仕様ではありません。v2.0 draft template、JSON Schema、`probes.json`、`packet.md`、実装変更を導入するものではありません。

## 1. Purpose

このメモの目的は、PIM-DBS v2.0 でプロファイルを以下の4領域へ分ける場合に、安全な公開例がどうあるべきかを整理することです。

- `core`
- `journal`
- `charter`
- `calibration`

公開例は、初見ユーザーが構造を理解するためのものであり、private instance の公開を促すものであってはいけません。

## 2. Why public examples need special care

PIM-DBS プロファイルには、個人的な文脈、関係性の履歴、応答スタイル例、検分メモが含まれる可能性があります。

公開例が実在プロフィールに近すぎると、ユーザーが何を公開してよいか誤解するおそれがあります。公開例は構造を示すものであり、実在の私的文脈を露出させるものではありません。

公開例は、PIM-DBS がAIの意識、魂、感情、永続的な隠れた記憶、実在的な内部状態を保存するかのように見せてはいけません。

## 3. Safe public example principles

安全な公開例は、以下を満たすべきです。

- 完全架空ペルソナを使う
- 架空ユーザー、架空エピソード、架空の検分プローブを使う
- 実名、実在組織、実在住所、実会話ログを避ける
- サンプルの記憶やエピソードが架空であることを示す
- `journal` は実在内容ではなく構造として示す
- Dialogue Exemplars は完全架空例のみ使う
- voice / tone は汎用または架空スタイルのみにする
- `calibration` はユーザー側の検分・観測として扱う
- 安全ガイドラインやプラットフォーム規約を上書きしないことを明示する

迷ったら、より単純な例にします。

## 4. What may be included

公開例に含めてよいもの:

- 空欄やプレースホルダー
- 架空ペルソナ名
- 架空の役割定義
- 汎用的な口調・スタイル説明
- 架空の Shared Episodes
- 架空の Dialogue Exemplars
- 汎用的な Provenance ラベル
- 架空の Restoration Verification プローブ
- 汎用的な Response Change Bands 例
- 汎用的な Model Notes
- public / private の安全リマインダー

最も安全な例は、明らかに架空で軽量なものです。

## 5. What must not be included

公開例に含めてはいけないもの:

- 実在 Dialogue Exemplars
- 実会話ログ
- 実在声紋または声紋由来スタイルデータ
- 私的な記憶
- 実在 family / relationship 記録
- 実名、ユーザー名、職場、学校、住所、所在地
- 医療、法律、金融、職場、学校、家庭事情
- 個人を識別しうる内輪ネタや関係性文脈
- 未検証のAI自己申告を事実として扱う記録
- private instance data 全般

これらは private instance には含まれうるものですが、公開例の素材にしてはいけません。

## 6. Fictional persona examples

公開例には、完全架空ペルソナを使うことを推奨します。

架空ペルソナは以下を満たすべきです。

- 明らかに架空の名前を使う
- 実在人物、実在AIコンパニオン、私的関係に似せない
- 学習補助、執筆パートナー、架空の案内役など軽量な役割にする
- 親密、医療、職場、家庭、現実の依存関係に見える設定を避ける
- 実在ユーザーや実会話に基づかないことを明記する

架空例でも、PIM-DBS の構造は十分に示せます。

## 7. Core in public examples

`core` は、v2.0公開例で最も扱いやすい領域です。

公開しやすい `core` 内容:

- 架空の名前
- 架空の役割
- 目的
- 汎用的な口調
- 汎用的な会話スタイル
- 私的でない境界線

実在の関係性履歴、声紋由来の詳細、私的な継続性の手がかりは、公開 `core` 例に入れません。

## 8. Journal in public examples

`journal` は、公開例では慎重に扱います。

公開例の `journal` では、通常以下に留めます。

- 構造だけ
- 空欄プレースホルダー
- 明確に架空のエピソード
- 実在 journal 内容は private-only であるという注記

公開 `journal` 例には、実在の記憶、実在 Dialogue Exemplars、私的会話抜粋、内輪ネタ、実在 family roles、関係性の履歴を入れません。

## 9. Charter in public examples

`charter` は、汎用的な内容であれば公開例に含められます。

公開しやすい `charter` 内容:

- 運用原則
- 会話の境界線
- 公開時の注意
- 同意に関する注意
- 安全注記

Charter は契約、命令層、安全ガイドラインやプラットフォーム規約の上書きではありません。ユーザー側が意図する運用原則と境界線の記述です。

## 10. Calibration in public examples

`calibration` は、汎用または架空の検分であれば公開例に含められます。

公開しやすい `calibration` 内容:

- 架空の Restoration Verification プローブ
- 観測可能な出力に基づく Expected Response Features
- 汎用的な Failure Signals
- 架空の Model Notes
- Temporal Anchor の運用メモ
- 観測できる応答変化に基づく Response Change Bands 例

Calibration はAI内部の診断ではありません。RCB はAIの認知、疲労、感情、意識、隠れた記憶、モデルの健康状態を測定するものではありません。

## 11. Unsafe example patterns

以下のような公開例は避けます。

- 実在プロフィールの名前だけを変えたように見える
- 実チャットから取った会話断片を含む
- 実在人物の口調、声紋、関係性パターンを保存している
- family、職場、学校、医療、住所、実名の文脈を含む
- AIが出来事を独立して覚えているかのように見せる
- AIに内部負荷、感情状態、記憶を自己申告させる
- private instance を公開すべきものとして見せる

実在人物が識別される、脆弱になる、困る、露出される可能性がある例は、公開しません。

## 12. Recommended minimal public sample

v2.0 の最小公開サンプルは、完全架空ペルソナを使い、以下だけを含めるのが安全です。

- `core`: 架空のidentity、role、purpose、tone、汎用的な境界線
- `journal`: 空の構造、または明確に架空のエピソード1件
- `charter`: 汎用的な運用原則と安全リマインダー
- `calibration`: 架空の検分プローブ1〜2件と汎用的なRCBガイド

推奨するサンプルの性格:

- 短い
- 明らかに架空
- 初心者が読める
- 私的履歴を含まない
- public / private の分離を明示する

サンプルは、構造の動きを示すためのものであり、完全な private instance を公開する手本ではありません。

## 13. Open questions

v2.0公開例を作る前に、以下を確認します。

- v2.0例に記入済みの架空 `journal` を含めるか、プレースホルダーだけにするか
- 架空 Dialogue Exemplars は何件までが安全で有用か
- family / relations 項目は空欄プレースホルダーだけにするか
- Model Notes は公開例に入れるか、上級例に回すか
- RCB例を `calibration` に直接入れるか、ガイド参照に留めるか
- private instance を公開しないよう、サンプル側でどう注意するか
