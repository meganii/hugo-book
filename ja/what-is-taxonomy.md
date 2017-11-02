# Taxonomyとは？

Hugoではユーザが定義できるグルーピングのことを`Taxonomy`と呼んでいます。

`Taxonomy`と言われても初めは全然ピンと来ませんでしたので少し説明します。例えば、ブログでよく見られるパターンとして記事を「カテゴリ」と「タグ」で分類しているかと思います。

この「カテゴリ」と「タグ」という分類を`Taxonomy`と呼びます。この「カテゴリ」と「タグ」はよく使われるので、Hugoには初めから`categories`と`tags`が設定なしで利用できるようになっています。


例えば、タグの場合、FrontMatterに`tags: ['cat1','cat2']`という具合に、配列でタグを定義することができます。

```
---
title: "My First Post"
date: 2017-10-09T15:43:20+09:00
tags: ['cat1','cat2']
---

```

ビルドすると、以下の通りタグページが自動的に生成されます。

- http://localhost:1313/tags/
- http://localhost:1313/tags/cat1
- http://localhost:1313/tags/cat2



カテゴリの場合も同様です。`categories: ['books','life']`と配列で指定します。


```
---
title: "My First Post"
date: 2017-10-09T15:43:20+09:00
categories: ['books','life']
---

```

ビルドすると、以下の通りタグページが自動的に生成されます。

- http://localhost:1313/categories/
- http://localhost:1313/categories/books
- http://localhost:1313/categories/life

