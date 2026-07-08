# PIM-DBS v2.0 Field Mapping Note

この文書は、非規範的な設計メモです。v1.x の既存フィールドや概念を、v2.0候補構造へどう対応させるかを検討するためのものです。

これは確定した v2.0 仕様ではありません。v1.x プロファイルを無効化するものではなく、v2.0 draft template、JSON Schema、`probes.json`、`packet.md` を導入するものでもありません。

## 1. Purpose

このメモの目的は、PIM-DBS v2.0 でプロファイルを以下の4領域へ分ける場合に、v1.x の要素がどこへ対応するかを整理することです。

- `core`
- `journal`
- `charter`
- `calibration`

v2.0 実装に入る前に、曖昧な項目を減らすことを目的とします。

## 2. Mapping Principles

v1.x フィールドを v2.0候補構造へ対応させるときは、以下の原則を使います。

- v2.0 を v1.x の置き換え強制として扱わない。
- public template と private instance を混ぜない。
- 実在 Dialogue Exemplars、実会話、私的記録、声紋由来データを public template に入れない。
- Dialogue Exemplars は有用な概念として扱うが、実在内容は private-only とする。
- `calibration` はユーザー側の検分・観測層であり、AI内部診断層ではない。
- RCB は出力に現れる応答変化のユーザー側観測であり、AI内部状態の測定ではない。
- `charter` は運用原則と境界線であり、契約、命令層、安全規約の上書きではない。
- 何を非公開に留めるかは、ユーザーが管理できるようにする。

## 3. Proposed v1.x to v2.0 Mapping Table

| v1.xフィールド・概念 | v2.0対応候補 | public template可否 | メモ |
| --- | --- | --- | --- |
| Identity / name / role / basic profile | `core` | 架空または汎用なら可 | 安定したプロフィール識別子は `core` に置く。 |
| Voice / tone / speaking style | `core` または `journal` | 汎用または架空のみ可 | 汎用スタイルは `core`、実在声紋由来データは private-only。 |
| Values / boundaries / user-facing principles | `charter` | 汎用なら可 | 意図する運用と境界線を記述する。 |
| Provenance | `journal` と `calibration` | ラベル体系として可 | 記録文脈や検分データの出所を示す。 |
| Dialogue Exemplars | `journal` | 架空のみ可 | 実在 Dialogue Exemplars は private-only。 |
| Restoration Verification | `calibration` | 汎用または架空なら可 | 隠れた記憶ではなく、期待する応答特徴を確認する。 |
| Model Notes | `calibration` | 通常は非公開または匿名化 | 公開例では架空のModel Notesに留める。 |
| Temporal Anchor | `calibration` | 運用メモとして可 | ユーザーが与えるセッション参照であり、AI記憶ではない。 |
| Response Change Catalog | `calibration` | 可 | 観測される応答変化の参照資料。 |
| Response Change Bands / RCB | `calibration` | 可 | 粗いユーザー側観測帯域であり、内部状態の測定ではない。 |
| Self-Forge outputs | 確認後に分類 | 確認までは通常非公開 | AI生成の下書きは、ユーザー確認とprovenance確認が必要。 |
| private memories / episodes / relationship history | `journal` | 不可 | 完全架空化しない限り private instance に置く。 |
| public template placeholders | `core`, `charter`, `calibration` | 可 | 空欄、汎用、架空であれば安全。 |
| private instance data | `journal`、一部 `calibration` | 不可 | 原則として公開しない。 |

## 4. Core

`core` は、安定して再利用できるプロフィールデータを扱います。

候補:

- 名前または表示名
- 役割
- 目的
- 基本プロフィール
- 好ましい口調
- 一般的な会話スタイル
- 私的でない継続性の手がかり

`core` は、実在の私的履歴や識別可能な声紋由来データを含めない限り、公開テンプレートに最も向いています。

## 5. Journal

`journal` は、ユーザーが記録した文脈や私的履歴を扱います。

候補:

- Shared Episodes
- 実在する関係性の履歴
- 私的な記憶
- 実在 Dialogue Exemplars
- 私的な会話抜粋
- 内輪ネタ
- 日付つきの継続性メモ

公開文書では、`journal` は主に構造概念として説明します。実在内容は private-only とします。

## 6. Charter

`charter` は、運用原則と境界線を扱います。

候補:

- ユーザー向け原則
- 話題の境界線
- 安全リマインダー
- 公開ルール
- 同意ルール
- public / private の扱い

Charter はAIを拘束する契約ではありません。プラットフォーム規約や安全ガイドラインを上書きするシステムプロンプトでもありません。ユーザー側が意図する運用の記述として扱います。

## 7. Calibration

`calibration` は、ユーザー側の検分、観測、モデル別メモを扱います。

候補:

- Restoration Verification
- Verification Probes
- Expected Response Features
- Failure Signals
- Model Notes
- Temporal Anchor
- Response Change Catalog への参照
- Response Change Bands / RCB

Calibration はAI内部の診断ではありません。観測できる応答特徴を期待値と比べ、低リスクな次の対処を選ぶための層です。

## 8. Public Template vs Private Instance

public template には、空欄、汎用、匿名化済み、または完全架空の内容だけを入れます。

public template 候補:

- プレースホルダー
- 汎用的な `core` 項目
- 汎用的な `charter` 境界線
- 架空の検分プローブ
- 架空のRCBまたは応答変化例
- privacy と provenance に関する説明

private instance には、ユーザー固有の内容が含まれます。

private instance 候補:

- 実在エピソード
- 私的な記憶
- 実在 Dialogue Exemplars
- 関係性の履歴
- 個人的な Model Notes
- センシティブな検分プローブ
- family、職場、医療、住所、実名などの文脈

迷ったら、非公開にします。

## 9. Ambiguous Fields

一部の項目は、privacy によって対応先が変わります。

| フィールド・概念 | 対応候補 | 判断ルール |
| --- | --- | --- |
| Voice / tone | `core` または `journal` | 汎用スタイルは `core`、実在声紋由来データは private-only。 |
| Shared Episodes | `journal` または公開用の架空例 | 実在エピソードは private、架空例は public 可。 |
| Model Notes | `calibration` | 公開するなら架空、汎用、匿名化済みに限る。 |
| Self-Forge outputs | `core`, `journal`, `charter`, `calibration` への下書き | プロファイルデータとして扱う前にユーザー確認が必要。 |
| Provenance | `journal` と `calibration` | 出所の明確化が必要な場所で使う。 |
| Temporal Anchor | `calibration` またはセッションメモ | 永続記憶ではなく、セッション参照として使う。 |

## 10. Do Not Map to Public Template

以下は public template に対応させません。

- 実在 Dialogue Exemplars
- 実在会話ログ
- 実在声紋または声紋由来スタイルデータ
- 私的な記憶
- 実在人物の family / relationship 記録
- 医療、法律、金融、職場、学校、住所、実名の文脈
- 未検証のAI自己申告を事実として扱う記録
- private instance data 全般

これらは、ユーザーが意図的に保持する場合でも private instance に置くべきであり、公開仕様の素材にはしません。

## 11. Open Questions

v2.0 実装前に、以下を決めます。

- v2.0 はすぐ draft template を出すか、まず文書だけにするか
- `journal` はセクション、別ファイル、private-only概念のどれにするか
- `charter` は必須セクションにするか、任意レイヤーにするか
- RCB は `calibration` 内に保存するか、参照に留めるか
- Self-Forge と Guild Master の出力をどう確認してからマップするか
- v1.x プロファイルを、分割強制なしでどう移行するか
- private instance の公開を促さずに、どこまで公開例を出せるか
