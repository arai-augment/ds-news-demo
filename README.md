# ニュース更新のためし用サイト（Claude × GitHub）

Claudeに頼んでニュースを追加し、GitHubで承認すると公開される流れを試すためのサイトです。
サーバーは使わず、GitHub Pages（GitHubの無料の公開機能）で動きます。

## 1回目だけの準備
1. GitHubで新しいリポジトリを作る（名前の例：`ds-news-demo`。Public にする）
2. このフォルダの中身を、そのリポジトリにアップロードする
3. リポジトリの「Settings」→「Pages」を開き、
   「Source」を「Deploy from a branch」、ブランチを「main」「/(root)」にして保存する
4. 1〜2分待つと、`https://ユーザー名.github.io/ds-news-demo/` でサイトが見られる

## ニュースを追加する流れ
1. Claude Code（デスクトップアプリ、または claude.ai/code）で、このリポジトリを開く
2. 「この受賞をニュースに載せて」と、内容（と写真）を伝える
3. Claudeが記事を作り、プルリクエスト（承認待ちの変更）を出す
4. GitHubでプルリクエストを開き、中身を確かめて「Merge pull request」を押す
5. 1〜2分で、dronesports.jp 側と rangle.jp 側の両方の一覧に載る

## 中身
- `_posts/`：ニュース記事（1記事＝1ファイル）
- `_layouts/`：記事と一覧の型（ここは触らない）
- `dronesports/`・`rangle/`：2つのサイトに見立てたニュース一覧
- `CLAUDE.md`：Claudeが守る作業ルール

## 試してわかること
- 管理画面にログインせず、Claudeとのチャットだけで記事が増えるか
- 型に流し込むので、見た目が崩れないか
- 承認（マージ）するまで公開されないか
- 1つの記事が2つの一覧に同時に載るか

## 試せないこと
- 承認する前の確認用ページ（GitHub Pagesにはない。Cloudflare Pagesなら変更ごとに確認用URLが出る）
