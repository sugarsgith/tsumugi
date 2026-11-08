# 保健室のつむぎ v2

昼休みと放課後の保健室を舞台に、ばらばらの証言を時間と人物の表へ戻していく、単一 HTML の小さなゲームです。正式な題は「保健室のつむぎ v2 — 拡張するタイムライン」。画面上の名前は「保健室のつむぎ」、肩書きは「AI相談員 つむぎ · Prototype 02」です。

ビルドはありません。ブラウザが `index.html` を開くだけで動きます。

## 公開 URL

GitHub Pages が `main` ブランチのルートを配信します。

| 版 | ファイル | URL |
| --- | --- | --- |
| 本番 | `index.html` | https://sugarsgith.github.io/tsumugi/ |
| テスト | `test/index.html` | https://sugarsgith.github.io/tsumugi/test/ |

テスト版は本番と同じゲームに、画面右上の固定バッジ「テスト版」だけを足したものです。バッジは `TEST-BADGE-START` から `TEST-BADGE-END` までのひと塊で、ゲームの処理とは分かれています。

## フォルダ

```
.
├── index.html            本番。公開サイトの正面
├── test/index.html       テスト版。バッジ以外は本番と同じ内容から作業を始める
├── .nojekyll             Jekyll を使わないための空ファイル
├── README.md             このファイル
├── AGENTS.md             AI が手を入れるときのルール
├── CLAUDE.md             AGENTS.md への案内
├── CHANGELOG.md          変更履歴
└── docs/
    ├── GAME_SPEC.md      コードを読んだゲーム仕様
    └── KNOWN_ISSUES.md   直していない観察メモ
```

## ドキュメント

ほかの AI（Claude、ChatGPT など）にこのリポジトリを渡すときは、次を読ませてから手を入れさせてください。

- [ゲーム仕様](docs/GAME_SPEC.md) — 物語、グリッド、証言、勝ち、分岐、拡張、見た目、データの持ち方
- [既知の課題](docs/KNOWN_ISSUES.md) — ヒント不足、文章の揺れ、操作、アクセシビリティ。観察であり、修正済みではない
- [AI 向け作業ルール](AGENTS.md) — まずテスト版、承認後に本番へコピー、仕様と履歴の更新
- [変更履歴](CHANGELOG.md)

Claude は [CLAUDE.md](CLAUDE.md) から入り、同じルールに従います。
