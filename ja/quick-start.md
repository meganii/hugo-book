
# Hugoを試してみる

## 1. Hugoインストール

Macであれば、Homebrewからインストールすることができます。

```bash
$ brew install hugo 
$ hugo version
```


## 2. サイトを構築する

以下のコマンドを叩くと、デフォルトの構成でサイトを構築することができます。

```bash
$ hugo new site yoursite
```

`yoursite`は、自身のサイト名です。

## 3. テーマを適用する

サイトができたなら、何かしらのテーマを設定する必要があります。

```bash
$ cd yoursite
$ git init
$ git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke

# Hugoの定義ファイルであるconfig.tomlを編集。themeに"ananke"を追加
$ echo 'theme = "ananke"' >> config.toml
```


## 4. コンテンツを作成する

以下のコマンドを叩いてコンテンツを作成します。

```
$ hugo new posts/my-first-post.md
```

`content/posts/my-first-post.md`にmarkdownファイルが作成されています。中身をのぞいて見ましょう。

### content/posts/my-first-post.md

```markdown
---
title: "My First Post"
date: 2017-10-09T15:43:20+09:00
draft: true
---

```

"---"で囲まれている部分は、FrontMatterと呼ばれるものです。コンテンツのメタ情報をYAML形式で書くことができます。



## 5. プレピュー

コンテンツを作成した後は、プレピューで確認してみましょう。`hugo server`コマンドを叩くと、HTTPサーバが自動的に起動されてプレピューを行うことができます。

`-D`のオプションは、Draft(下書き)を含めてプレピューするものです。

```
$ hugo server -D
```

デフォルトだと http://localhost:1313/ でサイトが立ち上がっています。
ブラウザで見て見ましょう。





