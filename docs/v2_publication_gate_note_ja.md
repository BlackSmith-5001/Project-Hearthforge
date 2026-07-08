# PIM-DBS v2.0 Publication Gate Note

これは、現在の PIM-DBS v2.0 設計資料を公開導線に載せる前の、内部用 publication gate note です。

release plan、v2.0仕様、README / CHANGELOG へ正式導線を追加する決定ではありません。v2設計群を内部に留めるか、静かに見つけられるようにするか、Draft / Preview として見せるかを判断するためのメモです。

## 1. Purpose

v2.0設計群には、構想メモ、フィールド対応、公開サンプル設計、架空サンプル、テンプレート形状、暫定決定、移行ガイド、内部インデックス、non-normative draft template が揃ってきました。

README / CHANGELOG にリンクを追加する前に、このメモで次を整理します。

- 現在存在する v2 assets
- 選べる publication options
- 維持すべき safety preconditions
- まだ公開導線に載せないもの
- v2設計群を外部に見せる前の確認項目

## 2. Current v2 Assets

現在の v2関連assets:

- [v2 Concept Study](v2_concept_study_ja.md)
- [v2 Field Mapping Note](v2_field_mapping_note_ja.md)
- [v2 Public Example Design Note](v2_public_example_design_note_ja.md)
- [v2 Minimal Fictional Sample](v2_minimal_sample_fictional_ja.md)
- [v2 Template Shape Note](v2_template_shape_note_ja.md)
- [v2 Draft Template Decisions Note](v2_draft_template_decisions_ja.md)
- [v2 Migration Guidance Note](v2_migration_guidance_note_ja.md)
- [v2 Internal Index](v2_index_ja.md)
- [v2 Draft Template](../templates/pim-dbs_v2_draft.json)

これらは、後続releaseで明示的に昇格されない限り、設計・レビュー用資料として扱います。

## 3. Publication Options

| Option | Description | Benefit | Risk |
| --- | --- | --- | --- |
| A. Keep internal for now | README / CHANGELOG にはまだリンクしない。 | 最も低リスク。v2レビューをmaintainersや近い協力者向けに留められる。 | 外部レビュー担当者がv2作業を見つけにくい。 |
| B. Add only v2 index as a quiet internal reference | 低強度の場所から v2 index だけへリンクする。 | 入口を1つに制御でき、v2をfinalに見せにくい。 | index自体が公開ロードマップのように読まれる可能性がある。 |
| C. Add a README section labeled v2 Draft / Preview | READMEに明確なdraft節を追加する。 | 関心のある読者がv2レビューをしやすい。 | 表現が弱いとv2.0 releaseのように誤読される。 |
| D. Create a formal release such as v1.7.0 with v2 draft notes | v2 notesをv1.x preview releaseとして出す。 | v1.xを維持したままversioned checkpointにできる。 | release notesで置き換えではないことを慎重に書く必要がある。 |
| E. Jump to v2.0-preview | 明示的なpreview lineとして出す。 | 大きな構造作業であることが伝わる。 | stable v2.0 specificationと誤解されるリスクが最も高い。 |

## 4. Recommended Option

現時点では、現在の資料を正式な v2.0 release として扱わない方が安全です。

安全な方向性は、v1.xを現行の正本経路として維持しつつ、v2 Draft / Preview として慎重に導線を置く案を評価することです。公開する場合、最初の入口は v2 index が有力です。その際は次のラベルを繰り返し明示します。

- non-normative draft
- preview
- final schema ではない
- v1.x replacement ではない
- public/private safety boundary を守る

このメモでは最終的な公開判断は行いません。

versioned release として出す場合、この段階では v2.0-preview よりも v1.7.0 などの v1.x 系releaseの方が安全です。v1.xを安定系として維持しつつ、v2資料を draft / preview として示せるためです。

## 5. README Exposure Options

READMEでの露出レベル候補:

1. まだREADMEリンクを追加しない。
2. Reference など低強度の場所に v2 index へのリンクだけを置く。
3. 安定した v1.x 利用導線の下に、小さな "v2 Draft / Preview" 節を置く。
4. draft template と migration guidance を再レビューした後で、より見えるv2節を検討する。

READMEに出す場合でも、安定した v1.x flow を先に置きます。v2が現在のテンプレート、ガイド、サンプル、Guild Master Demoを置き換えるように見せないことが重要です。

## 6. CHANGELOG / Versioning Options

versioning候補:

- まだCHANGELOGには書かない
- future / unreleased の v1.x セクションに "v2 design materials" として軽く書く
- v2 materials が draft / preview only であることを明記した v1.x release を作る
- `v2.0-preview` は、より磨いたcheckpointまで温存する

CHANGELOGに書く場合は、次を明記します。

- v1.xは引き続き有効
- v2 draftは任意
- v2 draftはfinal schemaではない
- v2 draftはvalidation standardではない
- v2 draftは必須置き換えではない

## 7. Safety Preconditions

v2資料をより広く見せる前に、次が保たれている必要があります。

- v1.x正本テンプレートは引き続き有効
- v2 draft は non-normative draft として表示されている
- v2 draft は final schema として説明されていない
- v2 draft は validation standard として説明されていない
- v2 draft は v1.x replacement として説明されていない
- public template と private instance を混ぜない
- 実在 Dialogue Exemplars、実会話ログ、声紋由来データ、私的記録を公開しない
- public `journal` は空構造、placeholder、完全架空例に限定する
- RCBをAI内部状態の測定として説明しない
- `calibration` をAI内部診断として説明しない
- `system_loading_instruction` は上位指示、安全ガイドライン、利用規約を上書きしない

## 8. What Must Remain Clear

読者が次を理解できる状態にします。

- PIM-DBS はAIの意識・魂・実在記憶を主張しない
- v2構造は、ユーザー側文脈をより安全に分離するためのもの
- `journal` はprivacy-sensitiveな領域
- `charter` は契約や安全上書きではなく、運用原則の領域
- `calibration` はユーザー側の検分・観測レイヤー
- public example は空欄、汎用、匿名化済み、または完全架空に限る
- private instance material を public sample data にしない

## 9. What Not to Publish Yet

現在のv2 setとして、次はまだ公開導線に載せません。

- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2対応
- migration helper
- validation tooling
- private instance examples
- real Dialogue Exemplars
- real family or relationship data
- real conversation logs
- voiceprint-derived data

これらは後で検討できますが、現在の public-facing v2 navigation にはまだ含めません。

## 10. Preflight Checklist

README / CHANGELOG にリンクを追加する前の確認:

- v1.x正本テンプレートに差分がない
- v2 draft JSON が parse OK
- v2 index のリンクがすべて通る
- READMEに出す場合、Draft / Preview / non-normative を明記する
- CHANGELOGに出す場合、v1.x replacement ではないと明記する
- v2関連ファイルに private-only data が入っていない
- RCB、`calibration`、`system_loading_instruction` の安全境界が崩れていない
- public examples が空欄、placeholder、汎用、匿名化済み、または完全架空に留まっている
- documentationだけでrelease tagが implied されていない
- measurement / diagnosis / consciousness / override / soul / memory / internal state などの危険語が、否定・限定・安全説明の文脈以外で使われていないことを確認する。
- 新たに公開導線へ出すファイルについて、EN/JAの見出し・表・リンク・安全注記の整合を確認する。

## 11. Open Questions

公開前の未決事項:

- v2資料はもう1回レビューするまで internal に留めるべきか
- 最初の公開リンクは v2 index だけにするべきか
- v2露出は v1.7.0 のような v1.x release に紐づけるべきか
- `v2.0-preview` は、より磨いたcheckpointまで温存するべきか
- 初見ユーザーを混乱させずに、READMEでどこまで見せるべきか
- 外部レビュワーには draft template と migration guidance のどちらを先に読ませるべきか
