# Kyopro Encyclopedia of Algorithms

## これなに

競プロ用のアルゴリズムの解説を集めた百科辞典を目指しているサイトです。(試験運用中)

### 内容の方針

-   想定読者: AtCoder 黄色以上
-   具体例を列挙して察してもらうだけは避ける。数学的な証明を書いていきたい
-   できるだけ他のページには依存しない

### なぜ GitHub Pages なのか

コンテンツを GitHub 上で管理する半 wiki 形式です。このため、

-   プルリクエスト経由で、誰でも自由に記事の追加や修正を提案できるが、
-   プルリクエストのマージには承認が必要であり、記事の内容が保証される。
-   また、修正やレビューの過程がコミットログやレビューコメントなどの形で残る。

などのメリットがあります。
デメリットとしては、git や GitHub の操作ができる人しか編集に参加できないこと、GitHub の制約によりレビュー時の数式の表示がしんどいことが挙げられます。

他の形式の場合、ブログのような個人的なメディアで記事を書くと古い記事が時代遅れになったまま残りがちであり、編集がまったく自由な共有 wiki で管理すると著者や内容の質が曖昧になりがちです。これらの間を選ぶことでそれぞれの持つ問題を解決することを目標としています。

## Contribution

### 記事を修正する

軽微なものならプルリクエストを送ってください。
簡単には修正できないものなら issue を立ててください。
それぞれページの右下の「Edit this page」「Report issues」というリンクを使うと便利です。

### 記事を追加する (概要のみ)

[トップページ](https://kmyk.github.io/algorithm-encyclopedia/) の目次にのみ項目を追加する場合は以下のようにします。

1.  [_entries/](https://github.com/kmyk/algorithm-encyclopedia/tree/gh-pages/_entries) ディレクトリの中に Markdown ファイルを追加する
    -   他の概要のみのページのためのファイルをコピペしてくればよい
1.  追加した Markdown ファイルを編集する。
1.  プルリクエストを送る。

### 記事を追加する (本文含む)

個別の記事ページ ([例](https://kmyk.github.io/algorithm-encyclopedia/monotone-minima)) を追加する場合は以下のようにします。

1.  上記の「記事を追加する (概要のみ)」と同様にして、トップページの目次に項目を追加する。
1.  対応する項目の Markdown ファイルに本文を追加する。
1.  プルリクエストを送る。

### メタデータの仕様

[front matter](http://jekyllrb-ja.github.io/docs/front-matter/) に書くべき情報は以下の通りです。

-   `layout`: 常に `entry`
-   `author`: その記事を書いた人の名前 (AtCoder ID)
-   `reviewers` (空欄可): その記事をレビューした人たちの名前 (AtCoder ID)
-   `date`: その記事を初めて書いた日時 ([ISO 8691](https://ja.wikipedia.org/wiki/ISO_8601) で秒まで)。`$ date --iso-8601=seconds` を実行するとよい。例: `2020-07-09T00:00:00+09:00`
-   `updated_at` (空欄可): その記事を最後に修正した日時 ([ISO 8691](https://ja.wikipedia.org/wiki/ISO_8601) で秒まで)
-   `tags` (空欄可): タグの列
-   `algorithm` (空欄可): アルゴリズムについての概要
    -   `input` (空欄可): アルゴリズムへの入力
    -   `output` (空欄可): アルゴリズムからの出力
    -   `time_complexity` (空欄可): アルゴリズムの時間計算量
    -   `space_complexity` (空欄可): アルゴリズムの空間計算量
    -   `aliases` (空欄可): アルゴリズムの別名の列
-   `description`: アルゴリズムの概要。「（ここにアルゴリズムの名前が入る）とは、（ここにアルゴリズムの概要が入る）というアルゴリズムである。」という形の文から初めて数文ぐらいで書く感じで。KaTeX は使用可。HTML も使用可だがあまり推奨されない
-   `draft` (省略可): これが存在するとトップページからのリンクが貼られません。
-   `draft_urls` (省略可): 記事の本文の代わりになるリンク

### 手元でのテストについて

``` console
$ sudo apt install ruby-all-dev ruby-bundler
$ bundle install --path .vendor/bundle
$ bundle exec jekyll serve --incremental
# open http://127.0.0.1:4000
```
