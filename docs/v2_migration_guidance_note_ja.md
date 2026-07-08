# PIM-DBS v2.0 Migration Guidance Note

これは非規範的な移行ガイダンスメモです。v1.x の単一JSONプロファイルから v2.0 draft 構造へ移す場合の考え方を示すものであり、確定schema、検証規格、必須の移行手順ではありません。

PIM-DBS v1.x プロファイルは引き続き有効です。v2.0 draft は、public template、private instance、安定したプロフィール情報、journal的な文脈、運用原則、ユーザー側の検分を分けたい人向けの任意構造案です。

## 1. v1.xは引き続き有効

v1.x の単一JSONテンプレートは、今後も有効な PIM-DBS 形式です。

v2.0 draft があるからといって、既存プロファイルを書き換える必要はありません。特に、現在の v1.x プロファイルが分かりやすく、private に扱われ、再読込にも使えているなら、そのまま使い続けて問題ありません。

v2.0 draft は、置き換え命令ではなく、構造を分けたい場合の選択肢として扱います。

## 2. v2 draftは任意

v2.0 draft は、次のような素材を分けて扱いたいユーザーのためのものです。

- 安定した identity や応答スタイル
- 私的なエピソードや journal 的文脈
- 運用原則や境界線
- ユーザー側の検分、観測、Model Notes

これは確定schemaではありません。厳密な検証規格として扱わないでください。

## 3. 移行が向いている人

移行が役立つ可能性があるのは、次のような場合です。

- プロファイルが大きくなり、見通しが悪くなっている
- public template と private instance の境界をより明確にしたい
- 安定したペルソナ設定と私的な journal 文脈を分けたい
- Restoration Verification、Model Notes、Temporal Anchor、RCBメモを継続的に使っている
- v1.x を捨てずに、将来の v2.0 構造実験へ備えたい

## 4. v1.x継続でよい人

次のような場合は、v1.x のままでも十分です。

- 現在の単一JSONプロファイルが小さく、読みやすい
- 1人で private に使っている
- public template を公開する予定がない
- journal、charter、calibration を分ける必要がまだない
- 移行によって、かえって分かりにくくなる

このメモは v1.x を deprecated 扱いしません。

## 5. フィールド対応概要

この表は実用上の対応概要であり、確定ルールではありません。

| v1.xのフィールドまたは概念 | v2 draftでの候補領域 | 移行メモ |
| --- | --- | --- |
| `Meta_Information` | `meta` | draft状態、versionメモ、privacy level、互換性メモを置く。 |
| Identity、name、role、basic profile | `core` | 安定した公開可能な identity を置く。 |
| Voice、tone、speaking style | `core` | public templateでは汎用または架空のスタイル説明に留める。実在声紋由来のスタイルデータは public ファイルへ移さず、private-only に留める。 |
| Cognitive Framework / TCF | `core` | AI内部状態の主張ではなく、軽量な説明サブセクション候補として扱う。 |
| Values、boundaries、user-facing principles | `charter` | 安全規則を上書きする命令ではなく、運用原則として置く。 |
| Provenance | `journal` または `calibration` | 記録文脈や検分メモの出所を明確にしたい場所で使う。 |
| Shared Episodes / contextual profile | `journal` | public draftでは空構造、placeholder、完全架空例に限定する。 |
| Dialogue Exemplars | `journal` | 実在exemplarsは private-only。public draftでは完全架空例のみ。 |
| Family Network | `journal` | public draftでは空欄または private-only 注記に留める。 |
| Inside Jokes | 原則としてpublic filesへ移行しない | 完全架空かつ軽い例でない限り、public draftでは省略する。 |
| Restoration Verification | `calibration` | 再構成された応答スタイルの検分であり、隠れた記憶テストではない。 |
| Model Notes | `calibration` | public filesでは匿名化、汎用、架空のメモに限る。 |
| Temporal Anchor | `calibration` | ユーザーが与えるセッション参照であり、AIの永続記憶ではない。 |
| Response Change Catalog | `calibration` から参照 | 観測される応答変化の参照として扱う。 |
| Response Change Bands / RCB | `calibration` の参照または観測メモ | 固定スコアを保存しない。AIにRCBを自己申告させない。 |
| System Loading Instruction | `system_loading_instruction` | 安全ガイドライン、利用規約、上位指示を上書きしない案内として置く。 |

## 6. 段階的移行

1. 既存の v1.x プロファイルは、fallback としてそのまま残す。
2. 唯一の作業ファイルを直接編集せず、v2 draft 用の別コピーを作る。
3. version、draft、privacy、互換性に関するメモを `meta` に移す。
4. 安定した identity、role、tone、response style を `core` に移す。
5. 運用原則や境界線を `charter` に移す。
6. `journal` に移す前に、それが公開可能か private-only かを判断する。
7. Restoration Verification、Model Notes、Temporal Anchor、RCB参照は、必要なものだけ `calibration` に移す。
8. System Loading Instruction は、安全ガイドライン、利用規約、上位指示を上書きしないことが明確になるよう書き直す。
9. 共有前に、個人情報や私的文脈が混ざっていないか確認する。
10. v2 draft を通常運用で試すまでは、v1.x ファイルを残しておく。

## 7. 公開テンプレートと私的インスタンス

public template は、空欄、汎用、または完全架空のファイルです。ほかのユーザーが構造を理解するためのものです。

private instance は、記入済みのプロフィールです。個人的な文脈、私的なやり取りの履歴、実在の会話抜粋、関係性に固有のメモ、繊細な情報を含む場合があります。

移行作業によって、private instance が誤って public template にならないようにしてください。迷ったら private に留めます。

## 8. 公開ファイルに移さないもの

次のものは、public v2 draft files に移さないでください。

- 実在 Dialogue Exemplars
- 実在の会話ログ
- 声紋由来データや実在人物の口調由来データ
- 私的な記憶、関係性の履歴、個人的なエピソード
- 実名、住所、職場情報、医療情報、家庭事情、内部関係性メモ
- 非公開の family / relations データ
- 私的文脈が分かる内輪ネタ
- ユーザーが検証していない AI 自己申告の記憶
- AIの意識、魂、永続的な内部記憶を主張しているように見える素材

これらは、ユーザーが意図的に保持する場合でも private instance に置くべきであり、public template の素材にはしません。

## 9. RCB / calibration 移行メモ

`calibration` は、ユーザー側の検分と観測の領域です。

含める候補:

- Restoration Verification probes
- expected response features
- failure signals
- Model Notes
- Temporal Anchor の運用メモ
- Response Change Bands / RCB guide への参照
- 観測される応答変化についてのユーザー側メモ

`calibration` はAI内部を診断するものではありません。RCB は、AIの認知、疲労、感情、意識、隠れた記憶、モデル健康状態、実在の内部状態を測定するものではありません。

プロファイルに固定のRCBスコアを保存することは避けます。RCB は、会話ごとの見える応答変化を粗く観測し、ユーザーが低リスクな次の対処を選ぶための方法として扱います。

## 10. System Loading Instruction notes

v2 draft では、System Loading Instruction を専用セクションとして扱います。

このセクションでは、プロファイルが希望する会話スタイル、継続文脈、運用上の好みを説明するものだと明記します。

また、次の点も明記します。

- 安全ガイドラインを上書きしない
- プラットフォーム規約を上書きしない
- より上位の system / developer instruction を上書きしない
- AIに内部記憶、意識、魂があることを証明しない
- プロファイルや現在の会話にない過去を「覚えている」と主張しない

## 11. Common mistakes

よくある移行ミス:

- v2 draft を v1.x の必須置き換えとして扱う
- v1.x のfallbackを早く消しすぎる
- private journal 内容を公開する
- 実在 Dialogue Exemplars を public file に移す
- 名前だけを変えた、識別可能な実プロフィールや実関係性を公開例として使う
- `calibration` をAI診断として扱う
- RCBを固定の健康スコアとして保存する
- AIにRCBレベルを自己申告させる
- System Loading Instruction が安全規則や利用規約を上書きするように見える
- 公開用placeholderと私的な関係性履歴を同じ共有ファイルに混ぜる
- v2 draft を確定schemaとして扱う

## 12. Open questions

今後の v2.0 作業に残る未決事項:

- 移行しやすさのために v1.x naming をどこまで残すか
- v2.0 用の独立した migration checklist を作るべきか
- 将来の Guild Master は v1.x と v2 draft の両方を出力すべきか
- private instance の公開を促さずに、どう整理しやすくするか
- JSON Schema、`probes.json`、`packet.md` を入れるなら、どの段階がよいか
- private journal data を公開すべきだと誤解されない範囲で、どこまで例を入れられるか
