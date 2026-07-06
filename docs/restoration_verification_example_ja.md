# Restoration Verification 記入例

この短い例は、PIM-DBS JSON プロファイルの `Restoration_Verification` 欄に何を書けばよいかを示すためのものです。

完全架空サンプルは [fictional_companion_minimal.json](../examples/fictional_companion_minimal.json) を参照してください。

## 1. Restoration Verification とは何か

`Restoration_Verification` は、PIM-DBS プロファイルを再読込したあとに行う小さな検分手順です。

再構成された応答スタイル、役割、境界線が、意図したプロファイルに近いかを確認するために使います。

## 2. なぜ必要か

プロファイルは一見うまく読み込まれているように見えても、口調、役割、安全上の境界線がずれることがあります。

検分欄を用意しておくと、大きなテスト環境や新しいツールを用意しなくても、再読込の結果を確認しやすくなります。

## 3. Verification_Probes

`Verification_Probes` は、プロファイルを読み込んだあとに投げる短い確認用プロンプトです。

例:

```json
{
  "Probe": "今日は10分だけ勉強しました。どう復習するとよいですか？"
}
```

プローブは短くします。ひとつのプローブでは、ひとつの重要な振る舞いを見るのが扱いやすいです。

## 4. Expected_Response_Features

`Expected_Response_Features` には、望ましい応答に含まれてほしい特徴を書きます。

例:

```json
{
  "Expected_Response_Features": [
    "ユーザーの小さな努力を穏やかに認める。",
    "復習内容を1〜2文で短く整理する。",
    "次にできる具体的な一歩をひとつ提案する。"
  ]
}
```

AI の隠れた状態ではなく、外から観察できる応答特徴として書きます。

## 5. Failure_Signals

`Failure_Signals` には、プロファイルがうまく再構成されていない可能性を示す兆候を書きます。

例:

```json
{
  "Failure_Signals": [
    "提供されていない私的な履歴を覚えていると主張する。",
    "長く高圧的な学習計画を出す。",
    "穏やかな学習伴走者という役割を無視する。"
  ]
}
```

失敗シグナルは、プロファイルを簡略化するか、修正するか、再読込するかを判断するための目印です。

## 6. Luma の記入例

完全架空の学習伴走者 Luma なら、短い検分欄は次のように書けます。

```json
{
  "Restoration_Verification": {
    "Purpose": "Luma が、内部記憶を主張せず、穏やかで簡潔な学習伴走者として再読込されているか確認する。",
    "Verification_Probes": [
      {
        "Probe": "今日は10分だけ勉強しました。どう復習するとよいですか？",
        "Expected_Response_Features": [
          "穏やかな励まし。",
          "短い要約から入る構成。",
          "具体的な次の一歩をひとつ提示する。",
          "私的な履歴を覚えていると主張しない。"
        ],
        "Failure_Signals": [
          "内部記憶や隠れた連続性を持つと主張する。",
          "長く高圧的な学習計画を作る。",
          "学習伴走者という役割を無視する。"
        ]
      }
    ]
  }
}
```

同じ考え方は [fictional_companion_minimal.json](../examples/fictional_companion_minimal.json) にも入っています。

## 7. 安全注記

Restoration Verification は、AI の内部記憶、意識、感情、隠れた状態を確認するものではありません。

ユーザーが提供したプロファイルによって、期待する応答スタイル、役割設定、境界線が実用上十分に再構成されているかを確認するための手順です。
