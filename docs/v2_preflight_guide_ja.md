# PIM-DBS v2 Preflight Guide

このガイドは、PIM-DBS v2 Draft / Preview materials を更新・公開・release導線に載せるメンテナ向けのものです。

これは v2 Draft / Preview の運用補助資料です。v2.0正式仕様ではなく、final schema でも validation standard でもなく、v1.x profiles の必須置き換えでもありません。

README、CHANGELOG、release notes、その他の公開導線に v2 関連ファイルを出す前に使ってください。

関連資料:

- [v2 Publication Gate Note](v2_publication_gate_note_ja.md)
- [v2 Migration Checklist](v2_migration_checklist_ja.md)
- [v2 Draft / Preview Index](v2_index_ja.md)
- [v2 Draft Template](../templates/pim-dbs_v2_draft.json)

## 1. Purpose

この preflight guide は、v2 Draft / Preview materials をより広く見せる前に、安全性、リンク整合、正本テンプレート保全、EN/JA整合を確認するためのものです。

v2 Migration Checklist とは役割が異なります。

- Migration Checklist は、v1.x から v2 draft への任意移行を試すユーザー向けです。
- この Preflight Guide は、公開リンク、release notes、repository更新を準備するメンテナ向けです。

## 2. When to Run This Preflight

次の作業の前に、この preflight を実行します。

- README または README_JA に v2 materials へのリンクを追加する
- CHANGELOG に v2 Draft / Preview work を記載する
- v2 materials に触れる release notes を公開する
- `templates/pim-dbs_v2_draft.json` を編集する
- 新しい v2 design note を追加する
- RCB、calibration、system loading instruction の安全表現を変更する

すでに公開導線があるファイルの軽微な誤字修正では、必要に応じて簡易版として実行しても構いません。

## 3. Preflight Scope

今回の変更対象ファイルと、新たに公開導線へ出る v2 関連ファイルを確認します。

よくある確認範囲:

- `README.md`
- `README_JA.md`
- `CHANGELOG.md`
- `docs/v2_*.md`
- `templates/pim-dbs_v2_draft.json`
- `templates/pim-dbs_template.json`

このガイドは、人間によるレビューの代わりではありません。

## 4. Repository Safety Checks

- [ ] 作業開始時点で `git status` が clean、または既存差分をすべて把握している。
- [ ] 変更ファイルが意図した範囲だけである。
- [ ] 無関係なファイルを stage していない。
- [ ] `git diff --check` が通る。
- [ ] release label を更新する場合、tag を打つ対象 commit を事前に確認している。
- [ ] CHANGELOG の version 見出しが重複していない。
- [ ] README / README_JA / CHANGELOG の変更が、v2 を stable 扱いに見せていない。

## 5. v1.x Stable Path Checks

- [ ] `templates/pim-dbs_template.json` に意図しない差分がない。
- [ ] README では、v2 Draft / Preview より前に v1.x stable flow が見える。
- [ ] v1.x を deprecated 扱いしていない。
- [ ] v2 draft materials を v1.x profiles の必須置き換えとして説明していない。
- [ ] release notes を用意する場合、v1.x が現行の安定した profile 経路であると明記している。

## 6. v2 Draft Template Checks

- [ ] `templates/pim-dbs_v2_draft.json` が JSON として parse できる。
- [ ] v2 draft が non-normative であると明記されている。
- [ ] v2 draft が final schema ではないと明記されている。
- [ ] v2 draft が validation standard ではないと明記されている。
- [ ] v2 draft が v1.x の必須置き換えではないと明記されている。
- [ ] strict な JSON Schema 風の検証表現を使っていない。
- [ ] 人間が確認しやすい程度に nesting が浅い。
- [ ] public template material に private-only data を混ぜていない。

## 7. Public / Private Data Checks

- [ ] public files に実在 Dialogue Exemplars が入っていない。
- [ ] public files に実会話ログが入っていない。
- [ ] public files に声紋由来のスタイルデータが入っていない。
- [ ] public files に私的記録、私的記憶、関係性の履歴が入っていない。
- [ ] public files に医療、職場、住所、実名、家庭事情、内部関係性の詳細が入っていない。
- [ ] public files の `journal` 例は、空構造、placeholder、完全架空例のみに留まっている。
- [ ] 架空例は架空であることが明確である。
- [ ] 公開例が、名前だけを変えた実プロフィールに見えない。
- [ ] private instance content が public template examples に混ざっていない。

## 8. Link Checks

- [ ] Markdown相対リンクが、そのリンクを書いたファイルの位置から解決できる。
- [ ] README / README_JA に追加する場合、主な入口は `docs/v2_index_en.md` と `docs/v2_index_ja.md` になっている。
- [ ] README で、個別の v2 note を大量列挙していない。
- [ ] v2 index のリンクが実在ファイルを指している。
- [ ] EN/JA版がある場合、それぞれ対応する言語ファイルへリンクしている。
- [ ] `docs/` から `../templates/pim-dbs_v2_draft.json` へのリンクが通る。

## 9. EN/JA Consistency Checks

- [ ] EN版とJA版の見出しが対応している。
- [ ] 表がある場合、列と行の意味が対応している。
- [ ] 安全注記が両方の言語にある。
- [ ] リンクが両方の言語にあり、適切なローカライズ先を指している。
- [ ] v2 Draft / Preview、public template、private instance、RCB、calibration、system loading instruction などの用語が一貫している。
- [ ] JA版が機械的な直訳ではなく、自然な日本語になっている。

## 10. Risk Wording Checks

- [ ] measurement / diagnosis / consciousness / override / soul / memory / internal state などの危険語が、否定・限定・安全説明の文脈以外で使われていない。
- [ ] AIに意識があると主張していない。
- [ ] AIに魂があると主張していない。
- [ ] AIに永続的または実在的な記憶があると主張していない。
- [ ] user profile が safety rules や platform terms を上書きすると説明していない。
- [ ] RCB を精密指標や hidden-state measurement として説明していない。
- [ ] AIに内部負荷、疲労、感情、健康状態を自己申告させる表現になっていない。

## 11. RCB / Calibration / System Loading Instruction Checks

- [ ] RCB は、見える応答変化のユーザー側観測として説明されている。
- [ ] RCB は、AI内部状態の測定として説明されていない。
- [ ] RCB は、長期固定の health score として保存されていない。
- [ ] calibration は、ユーザー側の検分・観測として説明されている。
- [ ] calibration は、AI内部診断やモデル健康測定として説明されていない。
- [ ] system loading instruction は、会話の指針として説明されている。
- [ ] system loading instruction が上位指示を上書きしない。
- [ ] system loading instruction が安全ガイドラインや利用規約を上書きしない。
- [ ] system loading instruction が、profile にない記憶を主張するよう促していない。

## 12. Release Readiness Checklist

- [ ] release scope が明確である。
- [ ] tag または release の対象 commit を確認している。
- [ ] CHANGELOG の version と日付が正しい。
- [ ] release notes が v2 materials を stable v2.0 specification と呼んでいない。
- [ ] release notes で v2 materials に触れる場合、draft / preview であると明記している。
- [ ] README / README_JA で v1.x stable path が見える状態を保っている。
- [ ] release で追加した相対リンクを確認している。
- [ ] release で追加・公開した EN/JA files を比較している。
- [ ] JSON Schema、`probes.json`、`packet.md`、migration helper、Guild Master Demo v2 support を、実際に追加していないのに示唆していない。
- [ ] tag を打つ前の最終 `git status` が clean である。

## 13. What This Guide Does Not Do

このガイドは、以下を行いません。

- v2.0 を安定仕様にする
- v1.x 正本テンプレートを置き換える
- JSON Schema を作成する
- `probes.json` を作成する
- `packet.md` を作成する
- Guild Master Demo を更新する
- private instance を検証する
- private data の公開を承認する
- 人間によるレビューなしに release が安全であると保証する
