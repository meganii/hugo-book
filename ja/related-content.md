# Related Content 関連記事

`Hugo Version 0.27`から、ある記事に対する関連記事を扱うことができます。

[Hugo \| Hugo 0\.27: Fast and Flexible Related Content\!](https://gohugo.io/news/0.27-relnotes/)

例えば、以下のコード例だと、現在のページに関連のあるページ5つが`$related`のリストに入り、そのリストを`range`で繰り返し表示しています。このように関連記事を手軽に扱うことができます。

```html
{{ $related := .Site.RegularPages.Related . | first 5 }}
{{ with $related }}
<h3>See Also</h3>
<ul>
	{{ range . }}
	<li><a href="{{ .RelPermalink }}">{{ .Title }}</a></li>
	{{ end }}
</ul>
{{ end }}
```

## 関連記事の設定方法

1. 設定ファイルに関連記事用の設定を加える
1. 上記コードをテンプレートに追加する
1. Buildする


## 設定方法

Hugoの設定ファイル(`config.toml`)に、下記のような設定を記述します。

```toml
[related]
# Only include matches with rank >= threshold. This is a normalized rank between 0 and 100.
threshold = 80
# To get stable "See also" sections we, by default, exclude newer related pages.
includeNewer = true
# Will lower case keywords in both queries and in the indexes.
toLower = false
[[related.indices]]
name = "keywords"
weight = 150
[[related.indices]]
name  = "author"
toLower = true
weight = 30
[[related.indices]]
name  = "tags"
weight = 100
[[related.indices]]
name  = "date"
weight = 10
pattern = "2006"
```



## 各設定内容

各設定内容は以下の通りです。
[Hugo \| Related Content](https://gohugo.io/content-management/related/)


### threshold

0-100で設定する閾値です。低く設定すれば、関連コンテンツの数が多くなりますが、その分関連性は落ちます。

### includeNewer

関連コンテンツに現在のコンテンツ以降のものを含めるかどうかをtrue / falseで設定します。trueに設定することで、日付的に新しいものも関連コンテンツとして表示されます。

### toLower

インデックスとクエリを小文字のキーワードとして扱うかどうかをtrue / falseで設定します。trueにすることで、わずかながらのパフォーマンスロスでより正確な結果を得られる可能性があります。この設定は、インデックス毎での設定もできます。


## `[[related.indices]]`毎に設定する内容

### name

インデックスとして利用するものを指定します。サポートしているのは、`author`などの文字列やリスト(tags, keywordsなど)、そしてtime, dateといった日時のオブジェクトです。


### weight

どれだけこのパラメタが重要であるかを重み付けです。

### pattern

dateにのみ影響します。関連コンテンツを並べるとき、日にちが近いものを並べたいといったケースがあると思います。デフォルトでは、"2006"と１年のうちに発行されたページに重みがつきますが、"200601"とすることで、より細かく設定することもできます。

### toLower

上記の`toLower`と同様です。



