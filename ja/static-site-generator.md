# 静的サイトジェネレータのススメ

「今からブログを初めてみよう！」そう思いついたら、今ならどんな選択肢があるでしょうか？

まず初めに考えられるのは、はてなブログや、Livedoorブログなどの無料ブログサービスでしょう。これは始めるのが簡単で、アカウントさえ作れば、あとはブラウザ上で記事を書いて投稿するだけ手軽に始めることができます。

でもそのうち、独自ドメインで自分でブログを立ち上げて、Google AdsenseやAmazon Affliate Programを利用したいとなった場合は、結局移行しなければいけません。

例えばブログを有名どころであるWordpressで運用するときのことを考えてみましょう。

まずは、ドメインを取得して、サーバーをどこにするか選びます。レンタルサーバーなら初めからPHP+MySQLの構成がインストール済かもしれませんが、VPS(仮想プライベートサーバ)を借りて自分自身で構築するとなると、OSを選んで、PHPをインストールして・・・とブログを書き始めるまでにいろんな作業があります。

また、一度Wordpressの環境を作れば終わりではありません。セキュリティ対策のため、定期的にWordpressやPHP自身のセキュリティパッチを当ててあげる必要があります。WordPressのバージョンをあげたら、入れていたプラグインが動かなくなりまた手間が増える・・・。データベースのバックアップも考えてあげる必要もあります。

と、思いつくままを書くだけでも、記事を書いて公開するまでにやるべきことがたくさんありません。

**ぼくは、ただ単に文章を書いてWebに公開したいだけなのに、どうしてこんなことをしなければならないのでしょうか？**

そこで、静的サイトジェネレータの出番です。

## 静的サイトジェネレータとは？

古き良き時代は、HTMLをメモ帳で直書きしてFFFTPを使ってアップロードして公開していました。しかし、今同じ方法でやりたいかと言われると面倒なのでやりたくありません。

静的サイトジェネレータは、テンプレートエンジンなので自動的に定められた通りにHTMLを組んでくれます。

### メリット

- テキストファイルだけなので、管理が楽
- WordPressのように定期的にパッチを当てなくても大丈夫
- 基本的にHTML+CSS+Javascriptだけなのでサイトが軽い

### デメリット

- ユーザのリクエストに対して、動的に表示を制御できない
- 関連記事の表示などに苦労する
- WebUIの管理画面がないので、外出先から更新できない

ユーザに合わせて動的にサイト(ページ)を生成できないため、関連記事の表示などWordPressではプラグインを入れれば比較的簡単にできることが難しいです。また、WebUIの管理画面はないので、外出先から更新することができません。


## なぜHugo?

「速さは正義」

Hugoを利用する理由に、圧倒的に生成が早いという点が挙げられます。