# PIM-DBS v2.0 Index

これは、現在の PIM-DBS v2.0 設計資料を読むための内部インデックスです。

正式な公開導線、release note、v2.0仕様ではありません。v2.0の構想メモ、暫定決定、移行メモ、draft template を迷わず読むための目次です。

## 1. Purpose

v2.0関連の設計ファイルが増えてきたため、このインデックスで次を整理します。

- 各ファイルの役割
- 推奨される読む順番
- v2.0の現在位置
- まだ含めていないもの
- 設計全体で守る安全境界

README では、このindexを v2 Draft / Preview の最小入口として使います。個別の v2 note は README に大量列挙しません。

## 2. Current Status

- v2.0はまだ正式仕様ではありません。
- v2 draft template は non-normative draft です。
- v1.x正本テンプレートは引き続き有効です。
- v2 draft は v1.x profiles の必須置き換えではありません。
- README では、v2 index を v2 Draft / Preview の最小入口として使います。
- v2関連ファイルは、明記がない限り設計・レビュー用の資料です。

## 3. Recommended Reading Order

1. [Concept Study](v2_concept_study_ja.md)
2. [Field Mapping Note](v2_field_mapping_note_ja.md)
3. [Public Example Design Note](v2_public_example_design_note_ja.md)
4. [Minimal Fictional Sample](v2_minimal_sample_fictional_ja.md)
5. [Fictional Migration Example](v2_migration_example_fictional_ja.md)
6. [Template Shape Note](v2_template_shape_note_ja.md)
7. [Draft Template Decisions Note](v2_draft_template_decisions_ja.md)
8. [Architecture Decision Note](v2_architecture_decision_note_ja.md)
9. [Stabilization Note](v2_stabilization_note_ja.md)
10. [v2 Draft Template](../templates/pim-dbs_v2_draft.json)
11. [Migration Guidance Note](v2_migration_guidance_note_ja.md)
12. [Migration Checklist](v2_migration_checklist_ja.md)
13. [Preflight Guide](v2_preflight_guide_ja.md)

この順番では、まず目的と範囲を確認し、その後に対応関係、公開サンプルの安全設計、架空サンプル群、テンプレート形状、暫定決定、architecture direction、stabilization direction、draft本体、移行ガイド、運用チェックへ進みます。

## 4. File Roles

| File | Role |
| --- | --- |
| [Concept Study](v2_concept_study_ja.md) | v2.0の目的、範囲、提案構造、安全境界、未決事項を整理する。 |
| [Field Mapping Note](v2_field_mapping_note_ja.md) | v1.xのフィールドや概念を、候補構造である `core`、`journal`、`charter`、`calibration` にどう対応させるかを整理する。 |
| [Public Example Design Note](v2_public_example_design_note_ja.md) | 公開サンプルで何を見せてよいか、何を入れてはいけないかを整理する。 |
| [Minimal Fictional Sample](v2_minimal_sample_fictional_ja.md) | 完全架空の worked example として、v2.0候補構造の最小例を示す。 |
| [Fictional Migration Example](v2_migration_example_fictional_ja.md) | v1.x風summaryからv2 draft structureへ分ける完全架空のmigration exampleを示す。 |
| [Template Shape Note](v2_template_shape_note_ja.md) | draft template の形状、top-level sections、未決の構造判断を検討する。 |
| [Draft Template Decisions Note](v2_draft_template_decisions_ja.md) | 初回 v2 draft template 作成前に置いた暫定決定を記録する。 |
| [Architecture Decision Note](v2_architecture_decision_note_ja.md) | 「分離の力 vs 単一ファイルの優しさ」を扱い、Option B / Single-File Section Separation を v2.0 基本線として評価する判断メモ。v2.0 stable specification そのものではない。 |
| [Stabilization Note](v2_stabilization_note_ja.md) | Option B / Single-File Section Separation を v2.0 stable の基本線として確定し、既定フローを1枚JSONで始められる形に維持する安定化メモ。v2.0 stable specification 本体、final schema、validation standard ではない。 |
| [v2 Draft Template](../templates/pim-dbs_v2_draft.json) | 現在の non-normative single-JSON draft template。 |
| [Migration Guidance Note](v2_migration_guidance_note_ja.md) | v1.xを無効化せず、v2 draftへ任意移行するための手引き。 |
| [Migration Checklist](v2_migration_checklist_ja.md) | v1.x から v2 draft への任意移行を試すユーザー向けの安全チェックリスト。 |
| [Preflight Guide](v2_preflight_guide_ja.md) | v2 Draft / Preview materials を更新・公開・release導線に載せる前のメンテナ向け確認手順。 |

## 5. Design Notes

Design Notes は探索的な文書です。

実装前に、次の意図を明確にするために置いています。

- 安定したプロフィール情報と journal 的な私的文脈を分ける
- public template と private instance の境界を明確にする
- 実在 Dialogue Exemplars や私的データを公開例に入れない
- `charter` を契約や命令ではなく運用原則として扱う
- `calibration` をユーザー側の検分・観測として扱う
- 構造分離と初心者に優しい単一ファイル既定形のバランスを評価する
- Option B / Single-File Section Separation を v2.0 基本線として安定化する
- v1.x の利用経路を残す

## 6. Examples

Examples は、v2 Draft / Preview structure を理解するための、public-safe かつ完全架空の補助文書です。

これらは v2.0 stable specification、final schema、validation standard、v1.x profiles の必須置き換えではありません。

- [Minimal Fictional Sample](v2_minimal_sample_fictional_ja.md) は、完全架空の v2 worked example です。
- [Fictional Migration Example](v2_migration_example_fictional_ja.md) は、v1.x風summaryからv2 draft structureへ分ける完全架空のmigration exampleです。

## 7. Operational Guides

Operational Guides は、v2 Draft / Preview materials を使う人・保守する人のための運用補助資料です。

これらは v2.0 を安定仕様にするものではありません。

- [Migration Checklist](v2_migration_checklist_ja.md) は、v1.x から v2 draft への任意移行を試す際、private-only material を public files に入れないための確認に使います。
- [Preflight Guide](v2_preflight_guide_ja.md) は、v2 materials をより広く公開する前に、安全性、リンク、正本テンプレート保全、EN/JA整合をメンテナが確認するために使います。

## 8. Draft Template

draft template は次の位置づけです。

- 単一JSONファイル
- non-normative
- final schema ではない
- validation standard ではない
- v1.xの必須置き換えではない

現在の top-level sections:

- `meta`
- `core`
- `journal`
- `charter`
- `calibration`
- `system_loading_instruction`

このdraftによって、v1.x正本テンプレートは変更されません。

## 9. What Is Not Included Yet

現在の v2.0 設計資料には、次は含まれていません。

- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2対応
- validation tooling
- migration helper
- README / CHANGELOG 正式導線
- tag / release

これらは今後検討できますが、現在の v2 design set には含めません。

## 10. Safety Boundaries

v2.0関連資料全体で、次の境界を守ります。

- AIの意識・魂・実在記憶を主張しない。
- 実在 Dialogue Exemplars、実会話ログ、声紋由来データ、私的記録を公開しない。
- public template と private instance を混ぜない。
- RCBはAI内部状態の測定ではなく、見える応答変化のユーザー側観測として扱う。
- `calibration` はAI内部診断ではなく、ユーザー側の検分・観測として扱う。
- System Loading Instruction は、安全ガイドライン、利用規約、上位指示を上書きしない。
- v1.xをdeprecated扱いしない。

## 11. Suggested Next Steps

次の候補:

- v2関連ファイルの抜け漏れがないか確認する
- v2 docs を当面 internal-only に留めるか判断する
- draft template と migration guidance の整合を確認する
- v2 draft が安定してから README 導線を検討する
- JSON Schema、`probes.json`、`packet.md` を v2.0 に入れるか、後続へ回すか判断する
