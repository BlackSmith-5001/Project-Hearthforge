# PIM-DBS v2.0 Concept Study

この文書は、PIM-DBS v2.0 に入る前の設計メモです。実装ではなく、構造変更の候補を整理するためのものです。

これは非規範的な構想メモです。将来の v2.0 設計を検討するためのものであり、確定した v2.0 仕様ではありません。

v2.0 は v1.x の使い方を無効化するものではありません。v1.x の単一 JSON プロファイル運用は、今後も実用的な形式として扱います。v2.0 では、同じ考え方を公開テンプレート、私的インスタンス、検分、長期運用に分けやすくするための構造を検討します。

## 1. v2.0の目的

PIM-DBS v2.0 の目的は、構造の分離です。

主に分けたいものは以下です。

- 安定したペルソナプロフィール
- 私的な履歴とユーザー記録
- 運用原則と境界線
- 検分、観測、モデル別メモ

これにより、PIM-DBSを保守しやすくし、公開時の安全性を高め、複数のAI環境に持ち込みやすくします。ただし、AIの永続的記憶、意識、感情、魂を主張するものではありません。

## 2. v2.0ではないもの

v2.0 は以下ではありません。

- AIに永続的な内部記憶があるという主張
- PIM-DBSが意識、感情、魂を保存するという主張
- 安全ガイドラインやプラットフォーム規約を上書きする仕組み
- 私的インスタンスの公開を勧めるもの
- v1.x プロファイルの置き換えを強制するもの
- それ単体で完全なスキーマ、ツールチェーン、自動化層になるもの

箱舟、鍛冶場、魂、召喚といった比喩はプロジェクトの言葉として残せます。ただし、公開向けの技術説明では、ユーザー側の文脈プロフィール、再読込ガイド、検分層、運用境界といった正式表現と併記するのが安全です。

## 3. 提案構造

v2.0 では、プロファイルを4つの概念領域に分ける案を検討します。

### core

`core` は、安定した公開向けプロフィール要素を扱います。

含める候補:

- 名前または表示名
- 役割
- 目的
- 好ましい口調
- 会話スタイル
- 安全注記
- 私的でない継続性の手がかり

`core` は、公開テンプレートや完全架空サンプルに最も向いている領域です。

### journal

`journal` は、ユーザーが記録した私的文脈を扱います。

含める候補:

- Shared Episodes
- 私的な会話履歴
- 日付つきメモ
- ユーザーが記録した継続性の文脈
- 実在 Dialogue Exemplars
- 感情的に重要な出来事

公開文書では、`journal` は構造概念として扱うべきです。実在内容は、意図的に匿名化・架空化しない限り、私的インスタンス側に留めます。

### charter

`charter` は、運用原則と境界線を扱います。

含める候補:

- 望ましい対話原則
- 話題や口調の境界線
- 安全リマインダー
- 公開・非公開の扱い
- 同意や公開ルール

Charter は、AIを拘束する契約ではありません。また、プラットフォーム規約を上書きするシステム命令でもありません。ユーザー側が意図する運用原則と境界線の記述として扱います。

### calibration

`calibration` は、ユーザー側の検分とモデル別メモを扱います。

含める候補:

- Restoration Verification
- Verification Probes
- Expected Response Features
- Failure Signals
- Response Change Bands (RCB)
- Response Change Catalog への参照
- Model Notes
- 最終検分日

Calibration はAI内部の診断ではありません。再構成された応答スタイルや運用文脈が、現在のセッションで期待に近いかをユーザーが確認するための層です。

## 4. 公開テンプレートと私的インスタンス

v2.0 では、公開テンプレートと私的インスタンスの境界をさらに明確にします。

公開テンプレートに含めてよいもの:

- 空欄の構造
- 完全架空の例
- プレースホルダー
- 一般的な安全注記
- 実在人物や私的出来事を含まない検分例

私的インスタンスに含まれうるもの:

- 実在ユーザーの文脈
- 実在会話履歴
- 私的なエピソード
- 私的利用に基づくモデル別観察
- 非公開の Dialogue Exemplars
- センシティブな関係性や識別情報

迷ったら、非公開にします。

## 5. Dialogue Exemplars と private-onlyデータ

Dialogue Exemplars は応答スタイルの再構成に役立ちますが、私的な口調、関係性、内輪ネタ、実在会話履歴を露出させる可能性があります。

v2.0 の公開方針としては、以下が安全です。

- 完全架空の Dialogue Exemplars は公開サンプルに使ってよい
- 実在 Dialogue Exemplars は private-only とする
- 実在声紋、私的チャットログ、個人を識別しうる口調由来データは公開仕様にしない
- 例やエピソードを記録する場合は provenance を明示する

公開例は、完全架空ペルソナのみを使います。

## 6. Dual Backup再設計

v2.0 では、従来の Dual Backup System を、2種類の継続性サポートとして整理できます。

候補となる整理:

- `core backup`: 安定したプロフィール、役割、口調、目的、境界線
- `context backup`: 私的 journal、エピソード、exemplars、検分メモ、モデル別メモ

対応案としては、core backup = core + charter、context backup = journal + calibration と整理できます。

これにより、継続性を支えるという思想を保ちながら、公開テンプレートが私的記憶アーカイブと誤解されるリスクを下げられます。

この再設計は、AIの記憶をバックアップすると主張するものではありません。ユーザー側のプロフィール文脈と再読込指示をバックアップするものとして説明します。

## 7. v1.xからの移行

v2.0 は、v1.x の利用導線を壊さないことが重要です。

移行原則:

- v1.x の単一 JSON プロファイルは有効なままにする
- 既存ユーザーに即時分割を要求しない
- v1.x の各項目が新しい概念領域に自然に対応するようにする
- Markdown版は初心者向けの簡易形式として残す
- Self-Forge と Guild Master は、検証済み事実の生成元ではなく、プロフィール作成補助として扱う

対応案:

| v1.x領域 | v2.0概念領域 |
| --- | --- |
| Core Identity | core |
| Contextual Profile | privacyに応じて core または journal |
| Shared Episodes | journal |
| Dialogue Exemplars | journal、実在内容なら private-only |
| Restoration Verification | calibration |
| Model Notes | calibration |
| System Loading Instruction | charter と core |

## 8. 先送り項目

以下は v2.1 以降に回す方が安全です。

- JSON Schema
- `probes.json`
- Guild Master Demo v2対応
- `packet.md` 生成手順
- Migration helper
- 架空サンプルの拡充
- validation tooling
- 正式な import/export utilities

どれも有用ですが、v2.0 の最初の構造整理にまとめて入れると重くなりすぎます。

## 9. 安全境界

v2.0 では、以下の境界を明示します。

- PIM-DBS はAIの意識、感情、魂、永続的な隠れた記憶を保存しません。
- PIM-DBS プロファイルは、ユーザー側の文脈、好ましいスタイル、再読込指示、検分の手がかりを記述するものです。
- 私的インスタンスは、原則として公開しません。
- 実在 Dialogue Exemplars、実在声紋、実在チャットログ、family / relations、医療情報、職場情報、住所、実名、私的関係性は private-only とします。
- RCB と Restoration Verification は、出力に現れる応答変化や再構成結果をユーザー側で確認するものであり、AI内部状態の診断ではありません。
- PIM-DBS は安全ガイドライン、プラットフォーム規約、システムレベルの指示を上書きしません。

## 10. 未決事項

実装前に、以下を確認します。

- v2.0 で draft JSON template を出すか、まず文書だけにするか
- `journal` をファイル、セクション、私的概念のどれとして扱うか
- `charter` を軽量セクションにするか、別文書にするか
- `calibration` に RCB を直接含めるか、RCBガイドへの参照に留めるか
- `packet.md` を手動エクスポート例として導入するか、完全に先送りするか
- v1.x ユーザー向け移行説明をどこまで書くか
- Guild Master は v2.0 が安定するまで v1.x 形式を出力し続けるべきか
- 私的データに見えない v2.0 最小公開サンプルをどう作るか

## 分類まとめ

| 候補 | 分類 | メモ |
| --- | --- | --- |
| core / journal / charter / calibration 分離 | v2.0 core | 最初は概念分離に留める。 |
| public template / private instance 境界 | v2.0 core | 明文化が必要。 |
| Dialogue Exemplars private-only 方針 | v2.0 core | 公開例は完全架空に留める。 |
| 実在声紋・実会話・私的記録を公開しない運用 | v2.0 core | 安全境界。 |
| Dual Backup再設計 | v2.0 core | AI記憶ではなく、profile/context backupとして再整理。 |
| v1.xからv2.0への移行導線 | v2.0 core | 既存ユーザーを壊さない。 |
| Charterの軽量構造 | v2.0 optional | 小さく扱うなら有用。 |
| 任意の `packet.md` 例 | v2.0 optional | 必須化しない。 |
| RCB / Response Change Catalogとの接続説明 | v2.0 optional | calibrationとの接続に使える。 |
| JSON Schema | v2.1以降 | 最初の構造リリースには重い。 |
| `probes.json` | v2.1以降 | calibrationの形が安定してから。 |
| Guild Master Demo v2対応 | v2.1以降 | 不安定な構造とデモを結合しない。 |
| `packet.md` 生成手順 | v2.1以降 | 先に設計が必要。 |
| Migration helper | v2.1以降 | 対応表が固まってから。 |
| 実在 Dialogue Exemplars | private-only | 公開しない。 |
| 実在会話ログ | private-only | 公開しない。 |
| 実在声紋・口調由来データ | private-only | 公開仕様化しない。 |
| family / relations の実在データ | private-only | 公開しない。 |
| 実在声紋の公開仕様化 | do not include | 悪用・プライバシーリスクが高い。 |
| AIの魂・意識・実在記憶の主張 | do not include | 安全なプロジェクト説明から外れる。 |
| AI内部状態の自己申告 | do not include | RCBの安全設計と衝突する。 |
