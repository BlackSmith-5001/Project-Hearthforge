# PIM-DBS v2.0 Template Shape Note

この文書は、非規範的な設計メモです。PIM-DBS v2.0 draft template を作成する前に、将来のテンプレート形状を検討するためのものです。

これは v2.0 draft template、JSON Schema、`probes.json`、`packet.md`、実装計画ではありません。v1.x の単一JSONテンプレートを無効化するものでもありません。

## 1. Purpose

このメモの目的は、PIM-DBS v2.0 が以下の候補構造を採用する場合、将来の draft template をどのような形にするかを整理することです。

- `core`
- `journal`
- `charter`
- `calibration`

実際の v2.0 テンプレートを作る前に、設計リスクを減らすことを目的とします。

## 2. Recommended Starting Shape

最初の v2.0 draft template は、単一JSONから始めるのが安全です。

理由:

- v1.x からの移行が分かりやすい
- 複数ファイル運用を早く導入しすぎない
- 初心者がコピー、保存、再読込しやすい
- ファイル分割を確定する前に v2.0 構造を試せる

複数ファイル化は将来的に有用ですが、v2.0構造が安定してから検討するのが安全です。

## 3. Candidate Top-level Sections

トップレベル構造の候補:

```text
meta
core
journal
charter
calibration
system_loading_instruction
```

これらの名前は設計候補であり、確定schema keyではありません。

## 4. Single JSON vs Multiple Files

最初の v2.0 draft template は、単一JSONが安全です。

単一JSONの利点:

- v1.x ユーザーに馴染みやすい
- public template として公開しやすい
- 手作業で確認しやすい
- 初期運用でprivate sectionを見失うリスクが低い

複数ファイルの利点:

- public / private の分離を強くできる
- `journal` を private-only として扱いやすい
- 将来の `packet.md`、migration helper、tooling と接続しやすい

推奨: まず単一JSON draftから始め、v2.1以降で任意のファイル分割を検討します。

## 5. Core

`core` はトップレベルセクションにする候補です。

扱う内容:

- identity
- role
- purpose
- tone
- general speaking style
- 私的でない継続性の手がかり

`core` は public template や完全架空サンプルに最も向いている領域です。実在の私的履歴や声紋由来データは入れません。

## 6. Journal

`journal` はトップレベルセクション候補ですが、public templateでは慎重に扱います。

public templateでの候補:

- 空構造
- プレースホルダー
- 明確に架空の短いエピソード
- private-only 注記

推奨: public templateでは空構造、または完全架空の1例に留めます。実在journal内容はprivate instance dataとして扱います。

実在 Dialogue Exemplars、実会話ログ、私的記憶、実在関係性履歴、family relations、声紋由来データを public `journal` 例に入れません。

## 7. Charter

`charter` は、v2.0 draft templateでは軽量必須セクション候補です。

理由:

- 安全境界を見える場所に置ける
- public / private の扱いを明確化できる
- 運用原則を命令ではなく原則として説明できる

Charter は契約、命令層、system prompt、安全ガイドラインやプラットフォーム規約の上書きではありません。ユーザー側の運用原則と境界線の記述です。

## 8. Calibration

`calibration` は任意だが推奨セクション候補です。

理由:

- 単純なプロフィールだけ必要なユーザーもいる
- 上級ユーザーには Restoration Verification、Model Notes、Temporal Anchor、RCB参照が役立つ
- 検分・観測をペルソナidentityから分離できる

Calibration はAI内部診断ではありません。観測できる応答特徴を確認し、低リスクな次の対処を選ぶためのユーザー側レイヤーです。

## 9. RCB Placement

RCB は、テンプレート内に永続的なスコアとして保存しない方が安全です。

推奨配置:

- `calibration.response_change_bands.reference`
- `calibration.response_change_bands.observation_notes`
- `calibration.response_change_bands.user_side_responses`

避けること:

- 固定RCB数値を保存する
- RCBをモデル健康度として扱う
- AIにRCBを自己申告させる
- RCBを内部状態の測定として扱う

RCB は、見える応答変化をユーザー側で観測するための、ガイド参照型の方法に留めます。

## 10. Meta Information

v1.x の `Meta_Information` は、トップレベルの `meta` セクションにする候補です。

理由:

- protocol version、profile version、author、target model、privacy status は persona identity ではない
- `meta` を分けると、`core` をプロフィール本体に集中させやすい
- 将来的に protocol version / schema or draft version / user profile version を分離しやすい

未決: v2.0 ですぐ `meta` に変えるか、v1.xとの馴染みを重視して最初のdraftでは `Meta_Information` を残すか。

## 11. Cognitive Framework / TCF

v1.x の `Cognitive_Framework` と TCF 関連概念は慎重に扱います。

配置候補:

- `cognitive_framework` セクションとして説明的に残す
- values や interaction principles を `charter` に寄せる
- 観測可能な検分を `calibration` に寄せる
- style や routine preferences を `core` に置く

推奨: 初期draftではTCFを細かく分散させすぎない。`core` 内の軽量 `cognitive_framework` subsection、または明確に説明的なセクションとして扱うのが安全です。

TCF はAI内部認知として説明しません。ユーザーが望む対話パターン、応答傾向、運用フレームとして扱います。

## 12. System Loading Instruction

`system_loading_instruction` は、専用のトップレベルセクションにする候補です。

理由:

- 運用上重要
- 再読込時にコピーしやすい
- 強い安全文言が必要

含めるべき内容:

- これはユーザー提供の文脈である
- 望ましい会話スタイルと境界線を記述する
- 安全ガイドライン、プラットフォーム規約、上位指示を上書きしない
- プロファイルにない記憶や内部状態を主張しない
- 時間文脈が不明な場合はユーザーに確認する

## 13. Family Network and Inside Jokes

`Family_Network` と `Inside_Jokes` は、public templateでは高リスク項目です。

public templateでは:

- 空欄プレースホルダーにする
- 明確に架空の例だけにする
- private-only 注記を入れる
- 実在family role、実在relationship map、私的ジョーク、識別可能な文脈を避ける

private instanceでは:

- ユーザーがプライバシーリスクを理解したうえでローカルに保持できる
- provenance と privacy note を明確にする

推奨: public v2.0 template にリアルな family / inside-joke 例を入れない。

## 14. v1.x Compatibility

v2.0 は v1.x の単一JSONテンプレートを無効化しません。

互換性説明で伝えること:

- v1.x プロファイルは引き続き使える
- v2.0 はより分けやすい構造案であり、強制置き換えではない
- 既存プロフィールをすぐ分割する必要はない
- v1.x フィールドは段階的に `meta`, `core`, `journal`, `charter`, `calibration` へ対応できる
- 初心者は簡易形式を使い続けられる

最初の v2.0 draft は、v1.x template と比較しやすい形にします。

## 15. Avoiding Schema-like Overcommitment

v2.0 draft template は、早い段階で最終schemaに見えすぎないようにします。

推奨する安全策:

- draft と明記する
- non-normative note を入れる
- 厳密なvalidation表現を避ける
- JSON Schemaを作るまでschema keywordを避ける
- 構造が確定済みであると主張しない
- 初回draftでネストを増やしすぎない

draft はレビューを促すものであり、v2.0が確定済みであると見せないようにします。

## 16. Open Questions

v2.0 draft template 作成前に決めること:

- 最初のdraftで `meta` を使うか、`Meta_Information` を残すか
- `charter` は必須か推奨か
- `calibration` は任意か推奨か
- `cognitive_framework` を名前付きセクションとして残すか
- `journal` に架空例を1件入れるか、プレースホルダーだけにするか
- `Dialogue_Exemplars` は `journal` 配下だけに置くか
- `Inside_Jokes` はpublic templateでは原則除外するか
- `Family_Network` は改名、最小化、private-only化のどれがよいか
- RCB は参照だけにするか
- 移行しやすさのため、v1.x名をどれだけ残すか

## 17. Provisional Shape Summary

暫定推奨:

```text
meta
core
journal
charter
calibration
system_loading_instruction
```

セクションごとの扱い:

| Section | 推奨ステータス | メモ |
| --- | --- | --- |
| `meta` | 必須候補 | persona identity から分離する。 |
| `core` | 必須候補 | 安定した公開向けプロフィール。 |
| `journal` | 任意 / privacy-sensitive | public templateでは空欄または架空のみ。 |
| `charter` | 軽量必須候補 | 運用原則と境界線。 |
| `calibration` | 任意だが推奨 | ユーザー側の検分・観測。 |
| `system_loading_instruction` | 必須候補 | 安全・規約・上位指示の制限を含める。 |
