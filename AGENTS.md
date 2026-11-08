# AI 向け作業ルール

このリポジトリは、単一 HTML のゲーム「保健室のつむぎ v2」です。Claude、ChatGPT、その他のエージェントは、手を入れる前にこのファイルと [docs/GAME_SPEC.md](docs/GAME_SPEC.md)、[docs/KNOWN_ISSUES.md](docs/KNOWN_ISSUES.md) を読んでください。

## どのファイルを編集するか

- ゲームの変更は、まず `test/index.html` だけに行う。
- `index.html` は本番です。`main` に載ると https://sugarsgith.github.io/tsumugi/ に出ます。オーナーが承認するまで更新しない。
- テスト版は https://sugarsgith.github.io/tsumugi/test/ に出ます。こちらは `test/index.html` を `main` に置けば公開されます。
- 本番へ昇格するときは、次の順で行う。
  1. オーナーの承認を得る。
  2. `test/index.html` を `index.html` にコピーする。
  3. コピー先の `index.html` から、`TEST-BADGE-START` から `TEST-BADGE-END` までのブロックを削除する。
  4. `test/index.html` 側のバッジは残す。
- 昇格後は、バッジのブロック以外、二つの HTML の中身が一致していること。
- バッジ用の `<style>` と `<div class="test-badge">` を、ゲーム本体の CSS やスクリプトに混ぜない。削除はブロックごと行う。

## ゲームの形を保つ

- ゲーム本体は、ビルドのない自己完結の HTML ファイル 1 枚に収める。外部の JavaScript や CSS を増やさない。いま読み込んでいる Google Fonts は残してよい。
- フレームワーク、パッケージマネージャ、変換工程を足さない。
- 既存の口調と日本語を保つ。意味を変える依頼でない限り、証言や解決文を言い換えない。
- 文体は話者で分かれている。陽向・芽衣はくだけた一人称、保健室の先生は丁寧な観察、莉子は丁寧寄り、解決の地の文は静かな常体。これを混ぜない。
- データの軸を崩さない。列は証言者、行は時間。拡張は配列を後から継ぎ足すのではなく、最初から定義してある 4 人と 3 つの時間を、`expanded` で見せる範囲を広げる実装になっている。
- [docs/KNOWN_ISSUES.md](docs/KNOWN_ISSUES.md) は観察メモである。頼まれていない項目を、ついでに直さない。直すときはそのメモも更新する。
- ライセンスファイルは、オーナーが決めるまで追加しない。

## 挙動を変えたら文書も変える

- プレイヤーから見える挙動、文章、勝ち条件、グリッド、操作を変えたら、同じ変更の中で [docs/GAME_SPEC.md](docs/GAME_SPEC.md) を実態に合わせる。
- 変更のたびに [CHANGELOG.md](CHANGELOG.md) へ日付と項目を追加する。最新を上に置く。
- 仕様に書いたこととコードが食い違ったら、コードに合わせて仕様を直す。仕様のほうを都合よく残さない。
