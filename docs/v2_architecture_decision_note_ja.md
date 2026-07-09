# PIM-DBS v2.0 Architecture Decision Note

これは非規範的な architecture decision note です。将来の PIM-DBS v2.0 stable specification を安定化するための設計入力であり、v2.0 stable specification そのものではありません。

この文書は、v1.x profile を置き換えず、final schema を定義せず、validation standard を作らず、現行の v1.x stable profile path からの移行を必須にしません。

## 1. Purpose

このメモの目的は、v2.0 の中心的な設計緊張を評価することです。

- 構造を分離する力
- 非技術者でも1ファイルから始められる優しさ

PIM-DBS v2.0 は、分離を強めながらも、既定フローを重くしすぎない必要があります。

## 2. Background

v2 Draft / Preview materials では、すでに以下の構造を検討してきました。

- `core`
- `journal`
- `charter`
- `calibration`
- `system_loading_instruction`

また、non-normative な単一JSONの v2 draft template と、運用補助資料も整備済みです。次の設計課題は、v2.0 stable の既定形を多ファイル構成に寄せるのか、それとも単一ファイルのまま内部セクションを明確化するのかを判断することです。

## 3. What v1.x Already Provides

v1.x には、すでに重要なユーザー側の仕組みがあります。

- Verification Probes
- Provenance
- RCB / Response Change Bands
- Temporal Anchor
- Dialogue Exemplars
- Migration Checklist

v2.0 はこれらを再発明するべきではありません。より明確な構造の中へ再配置するべきです。

つまり、v2.0 は既存の強みを失敗作や旧式扱いにせず、整理し直すものとして扱います。

## 4. Core Design Tension

多ファイル分離は強力です。

境界を明確にし、私的情報の誤公開を減らし、将来の context packet、migration helper、validator などのツールにもつなげやすくなります。

ただし、PIM-DBS の既定フローは、非技術者が1ファイルから始められるものであり続ける必要があります。

PIM-DBS の本来の優しさを失ってはいけません。ユーザーは、リポジトリ構成、schema、ファイル連携を理解していなくても、使える profile を保存できるべきです。

## 5. Option A: Two-Edition Model

Option A は、2つのエディションを定義する案です。

- Single-File Edition
- Workshop Edition

Single-File Edition は初心者向けの既定形です。Workshop Edition は、上級ユーザー、メンテナ、チーム向けに多ファイル整理を許容します。

利点:

- ユーザー段階ごとの説明がしやすい
- 将来の多ファイル運用を入れやすい
- 高度な public/private 境界を説明しやすい

リスク:

- どちらか一方が「本物」に見えてしまう
- ドキュメントが重くなる
- v2.0 が profile format ではなく product split に見える

Option A は魅力的ですが、stable v2 構造が固まった後の v2.x 拡張として扱う方が安全かもしれません。

## 6. Option B: Single-File Section Separation

Option B は、v2.0 stable の既定形を単一JSON profile としつつ、内部構造を分離する案です。

- `meta`
- `core`
- `journal`
- `charter`
- `calibration`
- `system_loading_instruction`

外部 journal file、shared relations file、context packet、workshop workflow は任意拡張に留めます。

利点:

- v1.x の単一ファイルの優しさを維持できる
- 最初の移行導線が単純になる
- v2.0 が早すぎる tooling platform に見えにくい
- public/private 分離に必要な構造は確保できる

リスク:

- ガイドを読まないユーザーが、1ファイル内に private material を入れてしまう可能性がある
- 任意拡張の整備が後回しになる
- 上級ユーザーはより強いファイル境界を早く求める可能性がある

Option B は、現在の v2 Draft / Preview の方向性とよく合っています。

## 7. Recommended Direction

現時点の推奨方向は、Option B を v2.0 stable の基本線として評価することです。

つまり:

- v2.0 は、内部セクション分離を強めた単一ファイル profile から始める
- v1.x は引き続き有効であり、deprecated 扱いしない
- multi-file workflow は任意・先送りにする
- Workshop Edition、shared relations file、context packet tooling は v2.x で検討する

このメモは最終決定ではありません。stable v2.0 specification を書く前の、現時点での architecture preference を記録するものです。

## 8. Required v2.0 Components

v2.0 stable には、以下の要素が必要と考えられます。

- manifest または `meta` による版数整理
- `core`、`journal`、`charter`、`calibration` のライフサイクル分離
- `charter` の独立した位置づけ
- journal の追記・distill 方針
- Model Notes から昇格した、ユーザー側の検分・観測層としての calibration
- 単なるフィールド名変更ではなく、意味を保つ v1.x migration
- 明確な public/private 境界

これらは、単一ファイルの既定 profile の中でも理解できる形にする必要があります。

## 9. Optional / Deferred Components

以下は任意または先送りが望ましい項目です。

- multi-file workflow
- shared relations file
- Context Packet tooling
- Guild Master Demo v2 support
- JSON Schema
- `probes.json`
- `packet.md`
- validation tooling
- migration helper

これらは将来的に有用ですが、最初の stable v2.0 scope に入れると、システムが必要以上に重く見える可能性があります。

## 10. What v2.0 Must Not Redesign

v2.0 は、以下の既存資産をゼロから再設計するべきではありません。

- RCB / Response Change Bands
- Provenance
- Verification Probes
- Dialogue Exemplars
- Temporal Anchor

これらは v2.0 architecture の中へ再配置するものであり、無関係な別システムへ改名したり、捨てられた v1.x の考えとして扱ったりしません。

## 11. Open Questions

- v2.0 stable の既定形式を "Single-File Edition" と呼ぶべきか、それとも v2.x まで edition という言葉を避けるべきか。
- journal distillation guidance は stable spec にどこまで含め、どこから別の operational guide に分けるべきか。
- `meta` は manifest に近い形にするべきか、軽量 metadata section のままにするべきか。
- public examples で private history の公開を誘導せずに `journal` をどう見せるべきか。
- Workshop / multi-file support を README レベルの導線に出す時期はいつがよいか。

## Safety Boundaries

- v1.x を deprecated 扱いしない。
- v2.0 を v1.x profile の必須置き換えとして提示しない。
- 既定フローを複雑にしない。
- 実在 Dialogue Exemplars、実会話ログ、声紋由来データ、私的記憶、実在の家族・関係性データを public examples に入れない。
- PIM-DBS は AI の意識・魂・実在記憶を主張しない。
- RCB を AI 内部状態の測定として説明しない。
- calibration を AI 内部診断として説明しない。
- `system_loading_instruction` は上位指示・安全ガイドライン・利用規約を上書きしない。
