# PIM-DBS v2.0 Draft Template Decisions Note

この文書は、非規範的な暫定決定メモです。PIM-DBS v2.0 draft template を作成する前に、仮の判断を記録するためのものです。

これは v2.0 draft template、JSON Schema、`probes.json`、`packet.md`、実装計画ではありません。ここでの決定は、レビュー後に変更される可能性があります。

## 1. Purpose

このメモの目的は、v2.0 draft template を作る前に、揺れやすい項目を減らすことです。

v2.0 Template Shape Note を前提に、最初のdraftに向けた暫定決定だけを記録します。

## 2. Decision Summary

| 項目 | 暫定決定 |
| --- | --- |
| Template form | 単一JSON draft template から始める。 |
| Top-level sections | `meta`, `core`, `journal`, `charter`, `calibration`, `system_loading_instruction` を候補にする。 |
| Metadata | 独立した `meta` セクションを採用する。 |
| v1.x `Meta_Information` | v1.x historical naming として扱い、v2 draftでは `meta` に寄せる。 |
| Charter | 軽量必須セクション候補にする。 |
| Calibration | 推奨セクション候補にする。 |
| Journal in public draft | 空構造または完全架空例に限定する。 |
| Cognitive Framework / TCF | top-levelではなく、軽量な `core.cognitive_framework` サブセクション候補にする。 |
| RCB | 固定RCBスコアを保存せず、guide reference と observation notes に留める。 |
| RCB paths | ドット記法パスは illustrative paths であり final keys ではない。 |
| System Loading Instruction | 安全・規約・上位指示の制限を含む専用セクションにする。 |
| Draft labeling | draft template には非規範的なドラフトであることを明記し、確定schemaや検証規格に見える表現を避ける。 |
| Family Network | public draftでは空構造または private-only 注記に留める。 |
| Inside Jokes | public draft では原則省略する。 |
| Dialogue Exemplars | public draftでは完全架空例のみ。 |
| Model Notes | `calibration` 内の架空・汎用例に限定する。 |
| v1.x compatibility | v1.x単一JSONプロファイルを無効化しない。 |
| Deferred tooling | JSON Schema、`probes.json`、`packet.md`、Guild Master Demo v2対応はv2.1以降に回す。 |

## 3. Top-level Sections

最初の v2.0 draft template は、以下のトップレベル構造を暫定候補にします。

```text
meta
core
journal
charter
calibration
system_loading_instruction
```

これらは候補セクション名であり、確定したschema keyではありません。

## 4. Metadata Decision

`meta` を独立したトップレベルセクションとして使います。

理由:

- metadata は persona identity ではない
- `core` をプロフィール本体に集中させやすい
- 将来的に protocol version、draft/schema version、profile version を分離しやすい

`Meta_Information` は v1.x historical naming として説明します。v2 draftでは対応関係に触れつつ、形状としては `meta` に寄せます。

## 5. Core and Cognitive Framework

`core` は安定したプロフィール情報を扱います。

- identity
- role
- purpose
- tone
- speaking style
- 私的でない継続性の手がかり

`Cognitive_Framework` / TCF は、最初のdraftでは独立したtop-level sectionにしません。必要な場合は、軽量な `core.cognitive_framework` サブセクション候補として扱います。

TCF はAI内部認知ではなく、ユーザーが望む対話パターンや応答フレーミングとして説明します。

## 6. Journal Decision

`journal` はトップレベル候補のままにしますが、public draftでは安全に扱います。

public draftに含めてよいもの:

- 空構造
- プレースホルダー
- 完全架空の短い例
- private-only 注記

public draftには、実在 Dialogue Exemplars、実会話、声紋由来データ、私的記録、実在関係性履歴、実在family data、医療文脈、職場文脈、住所、実名を入れません。

## 7. Charter Decision

`charter` は軽量必須セクション候補にします。

含める候補:

- 運用原則
- 境界線
- public / private の扱い
- safety reminder

Charter は契約、命令層、system prompt、安全ガイドライン、プラットフォーム規約、上位指示の上書きではありません。

## 8. Calibration Decision

`calibration` は必須ではなく、推奨セクション候補にします。

含める候補:

- Restoration Verification
- Model Notes
- Temporal Anchor usage
- Response Change Catalog references
- RCB guide references and observation notes

Calibration はAI内部診断ではありません。ユーザー側の検分・観測レイヤーです。

## 9. RCB Decision

RCB は、テンプレート内に固定スコアとして保存しません。

RCBは以下として扱います。

- guide reference
- observation note area
- user-side response planning aid

例示用のパス:

```text
calibration.response_change_bands.reference
calibration.response_change_bands.observation_notes
calibration.response_change_bands.user_side_responses
```

これらのドット記法パスは illustrative paths であり、final keys ではありません。

RCB はAI内部状態、認知、疲労、感情、意識、隠れた記憶、モデル健康状態の測定ではありません。AIにRCBを自己申告させません。

## 10. System Loading Instruction Decision

`system_loading_instruction` は専用トップレベルセクションにします。

含めるべき内容:

- これはユーザー提供の文脈である
- 望ましい会話スタイルと境界線を記述する
- 安全ガイドライン、プラットフォーム規約、上位指示を上書きしない
- プロファイルにない記憶や内部状態を主張しない
- 時間文脈が不明な場合はユーザーに確認する

## 11. Public-only Restrictions

public v2 draftでは、以下を制限します。

- `Family_Network`: 空欄、架空例、private-only注記に留める
- `Inside_Jokes`: 原則除外、または完全架空の軽い例のみ
- `Dialogue_Exemplars`: 完全架空例のみ
- `Model_Notes`: 架空または汎用例のみ
- `journal`: 空欄または架空のみ

public template と private instance を混ぜません。

安全デフォルト:

- `Inside_Jokes`: public draft では原則省略する。
- `Family_Network`: public draft では空構造または private-only 注記に留める。

## 12. v1.x Compatibility

v2.0 は v1.x の単一JSONプロファイルを無効化しません。

v2 draft は以下として説明します。

- 強制ではない構造案
- 移行しやすいdraft
- より分離しやすい構造モデル
- v1.xの強制置き換えではない

既存ユーザーに、即時の分割を求めません。

## 13. Deferred Items

以下は v2.1 以降に回します。

- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2対応
- migration helper
- validation tooling
- multi-file public/private workflow

これらは、v2 draft構造のレビュー後に扱います。

## 14. Still Open

以下は構造・命名レベルの未決事項であり、上記で示した public/private の安全方針を上書きするものではありません。

以下は引き続きレビュー対象です。

- final key names
- exact nesting depth
- `journal` に架空例を1件入れるか、プレースホルダーだけにするか
- `Inside_Jokes` をpublic draftに出すか
- `Family_Network` を改名・最小化するか
- 移行しやすさのために v1.x naming をどこまで残すか
- private instance のように見せずに、どこまでexample contentを入れるか
