# 全体的なスタイルルール

## プロトコル
埋め込みリソースからプロトコル表記(http:,https:)を省略する。
```html
<!-- NG -->
<scripts src="http://www.google.com/js/gweb/analytics/autotrack.js"></scripts>

<!-- OK -->
<scripts src="//www.google.com/js/gweb/analytics/autotrack.js"></scripts>
```

# 一般的な書式ルール
## インデント
タブ1つ分でインデントとする。タブとスペースを混在させるのはNG。
```html
<ul>
    <li>Fantastic
    <li>Great
</ul>
```

## 大文字/小文字
小文字のみを使用する。alt属性など値が文字列の場合は除く。
```html
<!-- NG -->
<A HREF="/">HOME</A>

<!-- OK -->
<img src="google.png" alt="Google">
```

## 文末のスペース
文末のスペースを削除する。
```html
<!-- NG -->
<p>What?_

<!-- OK -->
<p>Yes please.
```

# 全体的なメタデータ
## エンコード
エンコードは、UTF-8(BOM無し)を使う。
以下をHTMLファイルに記述してエンコード指定。
```html
<meta charset="utf-8">
```

## コメント
必要に応じてコードの説明を記述する。全部に書く必要は無い。
```html
<!-- headここから -->
<head>
</head>
<!-- headここまで -->
<!-- bodyここから -->
<body>
</body>
<!-- bodyここまで -->
```
## TODOコメント
コードにTODOをコメントとして記述する。その時"@"は使わない。
```html
<!-- TODO:内容at人 -->
```

# HTMLのスタイルルール
## ドキュメントタイプ
HTML5を使うこと。以下で始まる形式で書く。XHTML5はNG。
```html
<!DOCTYPE html>
```

## HTMLのバリデート(validate-妥当性確認-)
可能な限り適切なHTMLを記述すること。
そう書かないとパフォーマンスが低下する場合でない限りは、ちゃんと書く。
「[W3C HTML valodatpor](https://validator.w3.org)」などの検証ツールを使用する。
```html
<!-- NG -->
<title>Test</title>
<article>This is only a test.

<!-- OK -->
<!DOCTYPE html>
<mate charset="utf-8">
<title>Test</title>
<article>This is only a test.</article>
```


