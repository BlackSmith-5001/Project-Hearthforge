# PIM-DBS v2.0 Stabilization Note

これは、将来の PIM-DBS v2.0 stable specification に向けた非規範的な stabilization note です。

JSON Schema ではなく、validation standard でもなく、release note でもなく、最終的な v2.0 specification そのものでもありません。stable specification を書く前に、安定化の方向性を記録するための文書です。

## 1. Purpose

このメモの目的は、PIM-DBS v2.0 stable specification を書く前に、v2.0 の architecture direction を安定化することです。

Architecture Decision Note の判断を受けて、評価段階だった方向性を stabilization decision として扱います。

## 2. Background

v1.9.0 までに、以下の資料が整備されています。

- v2 Draft / Preview materials
- v2 draft template
- Migration Checklist
- Preflight Guide
- Fictional Migration Example
- Architecture Decision Note
- v2 Index navigation

これらにより、v2.0 を早すぎる重い tooling system にせず、stable direction を選べる段階に来ています。

## 3. Stabilization Decision

PIM-DBS v2.0 は、Option B / Single-File Section Separation を stable specification の基本線として採用します。

これは以下を意味します。

- 既定の profile は1枚の JSON ファイルから始める
- ファイル内部では明確な section 分離を行う
- multi-file workflow は既定経路ではなく任意拡張にする
- v1.x profile は引き続き有効であり、deprecated 扱いしない

この判断は、初心者に優しい既定形を守りながら、public/private 分離とライフサイクル整理を強化するためのものです。

## 4. Confirmed v2.0 Direction

v2.0 の方向性として、以下を確認します。

- 既定フローは1枚JSONから始められる形を維持する
- 明確な top-level structural areas を使う
- v1.x 既存資産を再発明せず、再配置する
- public/private 境界をより明確にする
- 任意の複雑さを stable baseline に入れすぎない

想定される stable direction は、現在の draft shape と互換です。

- `meta`
- `core`
- `journal`
- `charter`
- `calibration`
- `system_loading_instruction`

名称は今後微調整される可能性がありますが、構造の方向性は v2.0 specification 作業を進めるのに十分安定しています。

## 5. v2.0 Stable Scope

v2.0 stable scope には、以下を含めます。

- `meta` または manifest 相当の版数整理
- `core`、`journal`、`charter`、`calibration`、`system_loading_instruction` の構造分離
- `charter` の独立した位置づけ
- journal の追記・distill 方針
- loose な Model Notes から、ユーザー側の検分・観測層としての calibration への昇格
- 明確な public/private 境界
- 意味を保つ v1.x migration

stable scope は、ユーザーに multi-file workflow の採用を必須にしません。

## 6. Required Components

v2.0 安定化には、以下の要素が必要です。

- draft から stable への版数説明
- 各 top-level area の安定した説明
- public template に入れてよいもののガイド
- private-only に残すもののガイド
- v1.x を無効化しない migration language
- System Loading Instruction の安全説明
- AI内部診断に見えない calibration language
- AI内部状態の測定に見えない RCB language

これらは、v2.0 stable として release する前に stable specification の中で満たす必要があります。

## 7. Existing v1.x Assets to Reposition

以下の v1.x 既存資産は、v2.0 architecture の中に再配置します。

- Verification Probes
- Provenance
- RCB / Response Change Bands
- Temporal Anchor
- Dialogue Exemplars
- Migration Checklist

これらはゼロから再設計しません。

それぞれの役割を、必要に応じて `core`、`journal`、`charter`、`calibration`、または補助ガイドの中で明確化します。

## 8. Optional / Deferred Components

以下は任意または先送りとします。

- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2 support
- validation tooling
- migration helper
- multi-file workflow
- shared relations file
- Context Packet tooling

これらは v2.x で有用になる可能性がありますが、最初の v2.0 stable specification を止める条件にはしません。

## 9. Relationship to v1.x

v2.0 は v1.x を無効化しません。

v1.x は、v2.0 stable specification が release されるまでは current stable profile path として維持されます。また、その後も v1.x profiles は理解可能で、移行可能であるべきです。

v2.0 の目的は、既存 profile を罰することではありません。より強い分離が必要なユーザーに、明確な構造を提供することです。

## 10. Public / Private Boundaries

v2.0 stable は、public template と private instance の強い境界を維持します。

public template に入れてよいもの:

- 汎用的な profile structure
- 完全架空の examples
- public-safe placeholders
- private ではない tone / role descriptions

public template に入れてはいけないもの:

- 実在 Dialogue Exemplars
- 実会話ログ
- 声紋由来データ
- 私的記憶
- 実在の家族・関係性データ
- 医療、職場、住所、実名、家庭事情などの文脈

特に `journal` は注意が必要です。public files では空構造、placeholder、または完全架空例のみに留めます。

## 11. Safety Boundaries

PIM-DBS v2.0 は、以下の安全境界を維持します。

- AIの意識・魂・実在する永続記憶を主張しない
- RCB を AI内部状態の測定として説明しない
- calibration を AI内部診断や model health measurement として説明しない
- System Loading Instruction が上位指示・安全ガイドライン・利用規約を上書きするものにしない
- 実在する私的データを public examples に入れない
- v1.x を deprecated 扱いしない

PIM-DBS の比喩表現は残してよいですが、明確な技術的説明と併記します。

## 12. Preflight Conditions Before v2.0 Release

v2.0 stable release の前に、メンテナは以下を確認します。

- v1.x canonical template が引き続き利用可能である
- v2.0 stable wording が v1.x を deprecated と呼んでいない
- public examples が架空または placeholder の内容のみを含む
- v2.0 stable scope に JSON Schema が意図せず含まれていない
- EN/JA のリンクと見出しが対応している
- stable spec が AI の意識・魂・実在記憶を主張していない
- RCB と calibration がユーザー側の観測・検分層に留まっている
- System Loading Instruction の安全境界が明示されている

## 13. Open Questions

- stable v2.0 文書では `meta` と `manifest` のどちらの用語を使うべきか。
- journal distillation guidance は stable spec に含めるべきか、operational guide に分けるべきか。
- v2 draft template のどこまでを stable spec へ直接昇格させるべきか。
- v2.0 release に migration example を公式補助資料として含めるべきか。
- multi-file workflow はいつ v2.x optional extension として表に出すべきか。
