# PIM-DBS v2 Migration Checklist

このチェックリストは、v1.x の PIM-DBS profile を v2 draft structure へ移して試したいユーザー向けのものです。

これは v2 Draft / Preview materials の一部です。non-normative であり、final schema でも validation standard でもなく、v1.x profiles の必須置き換えでもありません。

v1.x profile 形式は引き続き有効です。`core`、`journal`、`charter`、`calibration`、`system_loading_instruction` に分けることで保守しやすくなる場合にのみ、このチェックリストを使ってください。

関連資料:

- [v2 Migration Guidance Note](v2_migration_guidance_note_ja.md)
- [v2 Field Mapping Note](v2_field_mapping_note_ja.md)
- [v2 Public Example Design Note](v2_public_example_design_note_ja.md)
- [v2 Draft / Preview Index](v2_index_ja.md)
- [v2 Draft Template](../templates/pim-dbs_v2_draft.json)

## 1. Purpose

このチェックリストは、private instance data を誤って public template material にしないよう、安全に移行を試すためのものです。

目的は、完璧な v2.0 profile を作ることではありません。v2 draft structure によって、安定したプロフィール情報、私的文脈、運用原則、ユーザー側の検分メモを分けやすくなるか確認することです。

まず軽く試すだけなら、最初は Section 2、Section 4、Section 10 から確認し、その後で全体のチェックリストを進めても構いません。

## 2. Before You Start

- [ ] 編集前に、元の v1.x profile のコピーを作る。
- [ ] 元の v1.x profile が引き続き有効で使えることを確認する。
- [ ] この移行が public template 用か private instance 用かを決める。
- [ ] フィールドを移す前に v2 Migration Guidance Note を読む。
- [ ] v2 Field Mapping Note で、各項目の配置候補を確認する。
- [ ] 何かを公開する前に v2 Public Example Design Note を確認する。
- [ ] v1.x profile を fallback として残しておく。
- [ ] v2 draft を final schema や validation standard として扱わない。

## 3. Migration Checklist

- [ ] v1.x のどの項目を `meta` に置くか確認する。
- [ ] 安定した identity、role、tone、style を `core` 候補にする。
- [ ] 私的、episode的、関係性に固有の素材を `journal` 候補にする。
- [ ] 運用原則と境界線を `charter` 候補にする。
- [ ] 検分、Model Notes、Temporal Anchor、RCB参照を `calibration` 候補にする。
- [ ] 現在の loading instruction を確認し、`system_loading_instruction` 用に書き直す。
- [ ] public files には public-safe な素材だけを移す。
- [ ] private-only material は private instance に留める。
- [ ] draft が final schema に見えるような名前変更を避ける。
- [ ] JSONで作業している場合は、編集後にJSON parseを確認する。

## 4. Public / Private Separation Checklist

- [ ] そのファイルが public 用か private 用かを確認する。
- [ ] public template placeholders と private instance history を混ぜない。
- [ ] 実在 Dialogue Exemplars を公開しない。
- [ ] 実会話ログを公開しない。
- [ ] 声紋由来データや実在人物の口調由来データを公開しない。
- [ ] 私的な記憶、私的記録、関係性履歴を公開しない。
- [ ] 医療、職場、住所、実名、家庭、内部関係性の詳細を公開しない。
- [ ] 私的文脈が分かる内輪ネタを公開しない。
- [ ] ユーザーが検証していないAI自己申告の記憶を公開しない。
- [ ] 迷ったら private に留める。

## 5. Core Checklist

- [ ] `core` は安定した identity、role、purpose、general style に絞る。
- [ ] public template では汎用または完全架空の style description を使う。
- [ ] 実在声紋由来の style data は private-only にする。
- [ ] 私的な関係性履歴を public `core` に入れない。
- [ ] cognitive framework notes は、AI内部状態の主張ではなくユーザー側説明として扱う。
- [ ] `core` を読みやすくし、過度に深くネストしない。

## 6. Journal Checklist

- [ ] `journal` は privacy-sensitive として扱う。
- [ ] public template では空構造、placeholder、完全架空例のみにする。
- [ ] 実在 episode、私的記憶、関係性履歴は private instance に留める。
- [ ] 出所が重要な文脈には provenance labels を使う。
- [ ] 実在 Dialogue Exemplars を public `journal` に入れない。
- [ ] 実在 family / relationship data を public `journal` に入れない。
- [ ] public `journal` が私的記憶アーカイブに見えないようにする。

## 7. Charter Checklist

- [ ] `charter` は運用原則と境界線に使う。
- [ ] `charter` をAIを拘束する契約として見せない。
- [ ] `charter` を command layer や system prompt として見せない。
- [ ] `charter` で安全ガイドライン、利用規約、上位指示を上書きしない。
- [ ] public `charter` 例は汎用、架空、匿名化済みに留める。
- [ ] public/private handling が分かる境界線を含める。

## 8. Calibration Checklist

- [ ] `calibration` はユーザー側の検分・観測として扱う。
- [ ] `calibration` をAI内部診断として扱わない。
- [ ] `calibration` をモデル健康測定として扱わない。
- [ ] 必要に応じて Restoration Verification probes を置く。
- [ ] Model Notes は汎用、匿名化、架空、または private の場合だけ置く。
- [ ] Temporal Anchor notes はユーザーが与えるセッション参照として置く。
- [ ] RCBは見える応答変化のガイドとして参照する。
- [ ] 固定RCBスコアを保存しない。
- [ ] AIにRCBレベルを自己申告させない。

## 9. System Loading Instruction Checklist

- [ ] profile がユーザー提供の文脈とガイドであることを書く。
- [ ] profile が安全ガイドラインを上書きしないことを書く。
- [ ] profile がプラットフォーム規約を上書きしないことを書く。
- [ ] profile が上位の system / developer instructions を上書きしないことを書く。
- [ ] ユーザーが提供していない記憶、内部状態、意識、感情、私的履歴をAIが主張しないように書く。
- [ ] 時間文脈が不確かな場合は、AIが推測せずユーザーに確認するように書く。
- [ ] 安全に再読込できる程度に簡潔にする。

## 10. Final Safety Review

- [ ] 元の v1.x profile が残っている。
- [ ] v2 draft が draft / preview / non-normative として表示されている。
- [ ] v2 draft が final schema として説明されていない。
- [ ] v2 draft が validation standard として説明されていない。
- [ ] v2 draft が v1.x の必須置き換えとして説明されていない。
- [ ] public files に private-only data が含まれていない。
- [ ] RCB が AI内部状態の測定として説明されていない。
- [ ] `calibration` が AI内部診断として説明されていない。
- [ ] `system_loading_instruction` が安全ガイドライン、利用規約、上位指示を上書きしていない。
- [ ] EN/JA両方を公開する場合、内容の整合が取れている。

## 11. What This Checklist Does Not Do

このチェックリストは、次のことをしません。

- v2.0 stable specification を作る
- JSON Schema を作る
- `probes.json` を作る
- `packet.md` を作る
- profile を自動検証する
- private data を自動で安全に移行する
- v2 draft を必須にする
- v1.x を deprecated 扱いする
- private instance の公開を許可する
