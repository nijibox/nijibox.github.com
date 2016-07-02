このブログの書き方（最短手順）

- `/blogs/`フォルダ以下に`{YYYYMMDD}-{BLOG_SLUG}.md`の形式でテキストファイルを作成します
  * テキストファイルの中身の1行目をブログのタイトルとして扱います
  * 2行目以降にブログ記事をMarkdownの書式で書き込みます
- `rake compile && git add -A && git commit -am {YOUR_COMMENT} && git push"`すれば投稿完了です

# 環境構築の流れ

## MacOSでDocker使わないパターン

```sh
brew install rbenv
rbenv install 2.3.1
rbenv local 2.3.1
gem install
# gem install --path vendor/bundle だとうまいことuglifierが読み込まれなかった…謎
rake compile
```
