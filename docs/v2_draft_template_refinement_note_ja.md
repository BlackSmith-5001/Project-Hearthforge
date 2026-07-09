# PIM-DBS v2 Draft Template Refinement Note

この文書は、現在の PIM-DBS v2 Draft / Preview template に対する非規範的な refinement note です。

これは v2.0正式仕様ではなく、final schema でも validation standard でもなく、v1.x profiles の必須置き換えでもありません。この文書だけでは `templates/pim-dbs_v2_draft.json` は変更されません。

関連資料:

- [v2 Draft Template](../templates/pim-dbs_v2_draft.json)
- [v2 Template Shape Note](v2_template_shape_note_ja.md)
- [v2 Draft Template Decisions Note](v2_draft_template_decisions_ja.md)
- [v2 Migration Checklist](v2_migration_checklist_ja.md)
- [v2 Preflight Guide](v2_preflight_guide_ja.md)
- [v2 Draft / Preview Index](v2_index_ja.md)

## 1. Purpose

このメモは、`templates/pim-dbs_v2_draft.json` を実際に編集する前に、改善候補を整理するためのものです。

目的は、今後の編集を小さく、レビューしやすく、安全に保つことです。

- draft status を明確にする
- public/private 分離を強める
- 人間が読みやすい形にする
- final schema や validation standard に見える表現を避ける
- 現行の v1.x stable path を維持する

## 2. Current Draft Status

現在の v2 draft template は、次の位置づけです。

- non-normative draft
- final schema ではない
- validation standard ではない
- v1.x profiles の必須置き換えではない
- レビューと試行のための single-JSON draft

v1.x 正本テンプレートである `templates/pim-dbs_template.json` は、引き続き有効です。

public template と private instance は分けたままにします。public draft material には、placeholder、空構造、完全架空例のみを使います。

## 3. Refinement Principles

今後の refinement は、次の原則に従います。

現行draftは、ここで挙げる安全条件の多くをすでに満たしています。そのため、refinement は全面的な作り直しではなく、増分的な磨き込みに留めます。

- 1回ごとの変更を小さくし、レビューしやすくする。
- draft が固定 schema に見える表現を避ける。
- public/private の境界を強める。
- v1.x を deprecated 扱いしない。
- 実在 Dialogue Exemplars や私的記録を public draft material に入れない。
- RCB は、AI内部状態の測定ではなく、見える応答変化のユーザー側観測として扱う。
- `calibration` は、AI内部診断ではなく、ユーザー側の検分・観測として扱う。
- `system_loading_instruction` は、上位指示、安全ガイドライン、利用規約を上書きしない。

## 4. Candidate Refinements

改善候補:

| Area | Candidate refinement | Reason |
| --- | --- | --- |
| `meta` | draft status と draft notice を明確にする。 | final schema と誤解されるリスクを下げる。 |
| `journal` | public placeholder と private-only note をより明確にする。 | 私的情報が public files にコピーされるリスクを下げる。 |
| `charter` | 軽量な運用原則を読みやすくする。 | charter を命令や契約ではなく、境界線と原則として保つ。 |
| `calibration` | user-side verification / observation としての説明を強める。 | AI内部診断に見えることを防ぐ。 |
| RCB references | RCB が固定スコア保存ではないことを示す注記を追加・調整する。 | RCB をモデル健康スコアではなく、応答変化観測として保つ。 |
| `system_loading_instruction` | 安全、利用規約、上位指示との境界を明確にする。 | override 的な解釈を避ける。 |
| `Family_Network` | public draft では空構造または private-only note に留める。 | 実在の家族・関係性データの露出を避ける。 |
| `Inside_Jokes` | public draft では原則省略を維持する。 | 内輪の文脈が例から漏れることを避ける。 |

これらは候補であり、draft template を変更する前に個別レビューが必要です。

## 5. Do Not Change Yet

最初の refinement pass では、次は変更しません。

- `templates/pim-dbs_template.json`
- v1.x 正本構造
- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2対応
- validation tooling
- migration helper
- multi-file workflow
- 実在 Dialogue Exemplars
- 実会話ログ
- 声紋由来データ
- 私的記憶、家族情報、関係性データ

## 6. Deferred Items

次の項目は、後続releaseで明示的にscope化するまで先送りします。

- formal JSON Schema
- validation tooling
- migration helper
- `probes.json`
- `packet.md`
- Guild Master Demo v2対応
- 任意の multi-file private instance workflow
- 公開用の完全架空サンプル拡充
- 詳細な calibration examples

これらは将来的には有用ですが、早く入れすぎると draft が確定仕様に見えやすくなります。

## 7. Safety Checks Before Editing the Draft

`templates/pim-dbs_v2_draft.json` を編集する前に、次を確認します。

- [ ] `git status` が clean、または現在の差分をすべて把握している。
- [ ] `templates/pim-dbs_template.json` に意図しない差分がない。
- [ ] 編集後も v2 draft が JSON として parse できる。
- [ ] draft が non-normative であると明記されている。
- [ ] draft が final schema ではないと明記されている。
- [ ] draft が validation standard ではないと明記されている。
- [ ] draft が v1.x profiles の必須置き換えではないと明記されている。
- [ ] public draft content に、実在 Dialogue Exemplars、実会話ログ、声紋由来データ、私的記録が入っていない。
- [ ] public の `journal` content は、空構造、placeholder、完全架空例に留まっている。
- [ ] RCB が長期固定スコアとして表現されていない。
- [ ] `calibration` が AI内部診断として説明されていない。
- [ ] `system_loading_instruction` が上位指示、安全ガイドライン、利用規約を上書きしていない。

## 8. Relationship to Migration Checklist

[v2 Migration Checklist](v2_migration_checklist_ja.md) は、v1.x から v2 draft への任意移行を試すユーザー向けの運用補助です。

refinement は、この checklist をより使いやすくする方向で行います。移行を強制したり、v1.x profiles が古くなったように見せたりしないようにします。

## 9. Relationship to Preflight Guide

[v2 Preflight Guide](v2_preflight_guide_ja.md) は、refine した v2 materials をより広く見せる前に使います。

draft template を編集した場合、preflight では次を確認します。

- リンク整合
- EN/JA整合
- v1.x 正本テンプレート保全
- public/private safety
- risk-wording safety
- release notes を用意する場合の release-readiness wording

## 10. Open Questions

今後の確認事項:

- 次の draft 編集は `meta`、`journal`、`calibration` のどこから始めるべきか。
- `Family_Network` は空構造として残すべきか、private-only guidance へ完全に寄せるべきか。
- `Inside_Jokes` は public drafts では常に省略すべきか。
- RCB guidance は draft 内にどこまで入れ、どこから外部ガイド参照に留めるべきか。
- AI内部診断に見えない範囲で、将来の架空サンプルに calibration examples を増やすべきか。
- JSON Schema を作るなら、いつが適切か。
