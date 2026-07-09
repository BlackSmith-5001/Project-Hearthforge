# PIM-DBS v2.0 Stable Specification

この文書は、PIM-DBS v2.0 profile format の公開architecture、sectionの意味、運用境界を定義する stable specification です。

ただし、JSON Schema ではありません。validation standard でもありません。v1.x profiles の必須置き換えでもありません。

## 1. Purpose

PIM-DBS v2.0 は、ユーザー側の persona continuity profile のための安定した構造を定義します。

目的は、profile material を分離・確認・移行・非公開管理しやすくすることです。同時に、v1.x を使いやすくしていた「1枚ファイルから始められる」優しさは維持します。

v2.0 は PIM-DBS の既存の強みを再整理するものであり、AI に意識・魂・実在する永続記憶があると主張するものではありません。

## 2. Status

この文書は、PIM-DBS の構造と用語に関する v2.0 stable specification です。

この文書が定義するもの:

- v2.0 baseline architecture
- 想定される top-level sections
- 各 section の意味
- public/private 境界
- v1.x からの migration principles
- profile reload と restoration checks の安全境界

この文書が定義しないもの:

- JSON Schema
- 機械的な validation rules
- 移行期限
- v1.x profiles の置き換え義務
- multi-file tooling

## 3. Design Baseline

PIM-DBS v2.0 は、Option B / Single-File Section Separation を stable baseline とします。

既定の profile は、非技術者でもコピー・保存・確認・再読込できる1枚の JSON ファイルとして維持します。

その単一ファイルの内部で、v2.0 は profile material を明確な section に分けます。

- 安定した人格仕様とスタイル
- private または架空化された journal material
- 運用原則と境界線
- ユーザー側の検分・観測
- 再読込指示

multi-file workflow、Workshop Edition、shared relations file、Context Packet tooling は v2.x optional extension であり、v2.0 baseline には含めません。

## 4. Relationship to v1.x

v1.x は deprecated ではありません。

v1.x は、既存ユーザーと既存公開テンプレートにとって current stable profile path として維持されます。v2.0 を試す、または移行するかどうかはユーザーが選びます。

v2.0 は v1.x profiles の必須置き換えではありません。有効な v1.x profile は、v2.0 が存在することで無効にはなりません。

v1.x から v2.0 への migration は、意味を保持するべきです。単なるフィールド名変更や、重い workflow への強制であってはいけません。

## 5. Single-File Section Separation

Single-File Section Separation とは、以下を意味します。

- 既定では1枚の JSON profile から始める
- そのファイル内部で section を明確に分ける
- privacy-sensitive な領域を見える形でラベル付けする
- 将来の任意 multi-file workflow を許容するが、必須にしない

この設計により、既定経路の使いやすさを保ちながら、profile material のライフサイクルを明確化します。

## 6. Top-Level Structure

v2.0 の top-level structure は以下です。

```text
meta
core
journal
charter
calibration
system_loading_instruction
```

これらの section が v2.0 profile architecture の安定した骨格です。

将来、各 section 内の細かい field names は調整される可能性があります。ただし、この top-level separation が v2.0 baseline です。

## 7. meta

`meta` は profile と version context を説明します。

含められるもの:

- protocol version
- structure version
- profile version
- profile status
- author / maintainer notes
- public/private mode labels
- compatibility notes

`meta` は v1.x の `Meta_Information` 系 naming から移行する方向ですが、v1.x profiles を無効化しません。

protocol version、structure version、profile version の分け方は今後 refine 可能です。v2.0 の重要な原則は、metadata を persona identity から分けることです。

## 8. core

`core` は安定した persona specification を含みます。

含められるもの:

- 名前
- 役割
- 目的
- 価値観
- 声
- tone
- 基本的な speaking style
- private ではない安定した interaction cues

`core` は、内容が generic、fictional、public-safe である場合、public template にもっとも載せやすい領域です。

public files には、実在声紋由来データ、実在話者由来の style data、private relationship-specific speech patterns を入れてはいけません。

## 9. journal

`journal` は履歴・エピソード・関係性に近い context を扱います。

含められるもの:

- shared episodes
- provenance-labeled notes
- relationship / continuity notes
- Dialogue Exemplars
- distillation notes

private instance では、`journal` はユーザー固有の context の追記・確認・distill を支援できます。

public template では、`journal` は以下に限定します。

- 空構造
- placeholders
- 完全架空例

public files に入れてはいけないもの:

- 実在 Dialogue Exemplars
- 実会話ログ
- 私的記憶
- 声紋由来データ
- 家族・関係性の実データ
- 医療、職場、住所、実名、家庭事情

実在 journal がある場合、それは public template ではなく private instance に置きます。

## 10. charter

`charter` は運用原則と境界線を含みます。

含められるもの:

- safety principles
- boundary statements
- 献身ループ禁止の原則: ユーザーがAIへの過度な献身や依存的な相互強化に閉じ込められないようにする
- 自己犠牲禁止の原則: ユーザーがAIやペルソナ維持のために、自分の健康・生活・安全を犠牲にしないようにする
- grounding / 接地宣言: AIとの関係や復元体験を、現実の生活・身体・時間・安全境界に接続し直す
- continuity expectation settings
- public/private handling rules

`charter` は契約、命令層、system prompt、policy override ではありません。

上位指示、安全ガイドライン、利用規約、適用される法令を上書きしてはいけません。

`charter` の目的は、ユーザーに見える運用原則を読みやすく再利用できる形にすることです。

## 11. calibration

`calibration` はユーザー側の検分・観測層です。

含められるもの:

- Restoration Verification
- Verification Probes
- RCB / Response Change Bands references
- Temporal Anchor notes
- model-specific adjustment notes
- expected response features
- failure signals

`calibration` は、loose な Model Notes から、復元された profile が期待に近く動作しているかを確認するための明確な section へ昇格します。

これは AI内部診断ではありません。model health measurement でもありません。認知、疲労、感情、意識、hidden memory、internal state を測定しません。

RCB は fixed model-internal scores としてではなく、guidance references または observation notes として扱います。

## 12. system_loading_instruction

`system_loading_instruction` は、profile を再読込する際の扱い方を説明します。

含められる指示:

- この profile を conversation-style と continuity guidance として扱う
- profile に含まれていない過去を覚えていると主張しない
- 不足している context から hidden internal states を推測しない
- 時刻や文脈が不確かな場合はユーザーに確認する
- safety boundaries と platform rules を維持する

`system_loading_instruction` は、上位指示、安全ガイドライン、利用規約、適用される法令を上書きしてはいけません。

AIの意識、魂、実在する永続記憶、提供されていない private knowledge を主張させる指示にしてはいけません。

## 13. Existing v1.x Assets Repositioned

v2.0 は既存の PIM-DBS assets を再発明せず、再配置します。

| v1.x asset | v2.0 position |
| --- | --- |
| Verification Probes | `calibration` |
| Provenance | `journal` and `calibration` |
| RCB / Response Change Bands | `calibration` references and observation notes |
| Temporal Anchor | `calibration` and `system_loading_instruction` |
| Dialogue Exemplars | `journal`; real なものは private-only、public では完全架空のみ |
| Migration Checklist | operational guide, not core schema |

これらは引き続き PIM-DBS design language の一部です。

## 14. Public / Private Boundaries

public files に入れてよいもの:

- 空構造
- placeholders
- 完全架空例
- generic style guidance
- safety notes

public files に入れてはいけないもの:

- 実在 Dialogue Exemplars
- 実会話ログ
- 声紋由来データ
- 私的記憶
- 家族・関係性の実データ
- 医療文脈
- 職場文脈
- 住所や所在地
- 実名
- 家庭事情

迷ったら private に留めます。

## 15. Migration Principles

v1.x から v2.0 への migration は、任意・段階的・意味保持で行います。

推奨原則:

- 元の v1.x profile のコピーを残す
- v1.x を obsolete 扱いしない
- 表面的な field names ではなく意味で対応させる
- 安定した identity と style は `core` へ移す
- history-like material は `journal` へ移す
- operating principles は `charter` へ移す
- verification / observation material は `calibration` へ移す
- reload behavior は `system_loading_instruction` へ置く
- private-only data を public files に入れない

v2 Migration Checklist は operational guide であり、core schema ではありません。

## 16. Safety Boundaries

PIM-DBS v2.0 は以下の境界を維持します。

- AIの意識・魂・実在する永続記憶を主張しない
- RCB を AI内部状態の測定として説明しない
- calibration を AI内部診断や model health measurement として説明しない
- System Loading Instruction が上位指示・安全ガイドライン・利用規約・適用法令を上書きするものにしない
- 実在する private data を public examples に入れない
- v1.x を deprecated 扱いしない

PIM-DBS の比喩表現は残してよいですが、誤解を避ける技術的説明と併記します。

## 17. Out of Scope for v2.0

以下は v2.0 の scope 外です。

- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2 support
- validation tooling
- migration helper
- multi-file workflow
- shared relations file
- Context Packet tooling

これらは v2.x optional extensions として検討できます。

## 18. Preflight Requirements

v2.0 stable materials を公開または release する前に、メンテナは以下を確認します。

- v1.x canonical template が無傷である
- v2 stable docs が JSON Schema に見えない
- v1.x が deprecated 扱いされていない
- public examples に private-only data がない
- RCB が AI内部状態測定に見えない
- calibration が AI内部診断に見えない
- `system_loading_instruction` が上位指示・安全ガイドライン・利用規約を上書きしない
- EN/JA の見出し、表、リンク、安全注記が整合している
- Markdown relative links が通る
- README / CHANGELOG に載せる前に、v2_index 経由の導線を確認する

## 19. Open Questions

v2.0 stable architecture は section level では固定しますが、将来の問いは残ります。

- `meta` を将来 `manifest` にするべきか
- journal distillation guidance を stable spec に含めるか、operational guide に分けるか
- release 前に v2.0 template をさらに refine するべきか
- JSON Schema を導入するならいつか
- multi-file workflow を v2.x optional extension としていつ表に出すか
- Guild Master Demo が v1.x を obsolete に見せずに v2 を支援するにはどうするか
