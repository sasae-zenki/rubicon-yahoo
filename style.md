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
## セマンティック(意味のある様に)に書く
目的に応じてHTMLを記述する。
見出しならhx要素、段落ならp要素、アンカーならa要素など目的に応じたHTML要素を使う。
リンクならa要素で書く。onclickのようなJavaScriptな振る舞いのものを要素の属性に入れない。
```html
<!-- NG -->
<div onclick="goToRecommendations();">All recommendations</div>

<!-- OK -->
<a href="recommendation/">All recommendations</a>
```

## マルチメディアの代替コンテンツ
マルチメディアの要素には、第垓コンテンツを提供する。
画像には、意味のある第垓コンテンツをalt属性として、動画・オーディオコンテンツにはキャプションを記述する。
装飾的な用途の場合など意味を持たない画像については、代替textは記述せずにalt=""とする。
```html
<!-- NG -->
<img src="spreadsheet.png">

<!-- OK -->
<img src="spreadsheet.png" alt="Spreadsheet screenshot">
```
## 構成要素の分離
文章構造・見た目・振る舞いは。分離すること。
見た目に関するものはスタイルシートに、振る舞いに関するものはスクリプトへ移して記述する。
```html
<!-- NG -->
  <!DOCTYPE html>
  <title>HTML sucks</title>
  <link rel="stylesheet" href="base.css" media="screen">
  <link rel="stylesheet" href="grid.css" media="screen">
  <link rel="stylesheet" href="print.css" media="print">
  <h1 style="font-size: 1em;">HTML sucks</h1>
  <p>I’ve read about this on a few sites but now I’m sure:
      <u>HTML is stupid!!1</u>
  <center>I can’t believe there’s no way to control the styling of
      my website without doing everything all over again!</center>

<!-- OK -->
  <!DOCTYPE html>
  <title>My first CSS-only redesign</title>
  <link rel="stylesheet" href="default.css">
  <h1>My first CSS-only redesign</h1>
  <p>I’ve read about this on a few sites but today I’m actually
      doing it: separating concerns and avoiding anything in the HTML of
      my website that is presentational.
  <p>It’s awesome!
```
## 実体参照
不要な実体参照は使用しないこと。
UTF-8においては、ー(&mdash;)・"(&rdquo)・☺(&#x263a;)のような文字は実体参照を使う必要はない。
HTMLで特別ない見を持つ文字(<や&など)は例外。
```html
<!-- NG -->
The currency symbol for the Euro is &ldquo;&eur;&ldquo;.

<!-- OK -->
The currency symbol for the Euro is "€".
```
## type属性
CSSとJavaScriptのtype属性は省略する。
HTML5ではデフォルトの言語として解釈されるため。
```html
<!-- NG -->
    <link rel="stylesheet" href="//www.google.com/css/maia.css" type="text/css">
<!-- OK -->
    <link rel="stylesheet" href="//www.google.com/css/maia.css">
```
```html
<!-- NG -->
    <script src="//www.google.com/js/gweb/analytics/autotrack.js"
    type="text/javascript"></script>
<!-- OK -->
    <script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```
# HTMLの書式ルール
## 全般的な書式
ブロック要素、リスト要素、テーブル要素は改行してから記述し、それらの子要素にはインデントを入れる。
横並びリストなど改行による空白が問題になうr場合は、li要素をすべて一行で書いてもOK。
```html
<blockquote>
    <p><em>Space</em>, the final frontier.</p>
</blockquote>
<ul>
    <li>Moe
    <li>Larry
    <li>Curly
</ul>

<table>
    <thead>
        <tr>
            <th scope="col">Income
            <th scope="col">Taxes
    <tbody>
        <tr>
            <td>$ 5.00
            <td>$ 4.50
</table>
```

# CSSスタイルシート
## CSSのバリデート
可能な限り適切なCSSを記述すること。
CSSバリデーターにバグがある場合は独自の構文を必要としない限りは、ちゃんと書く。
HTML同様「[W3C CSS validator](https://jigsaw.w3.org/css-validator/)」などのツールで検証する。

## IDとクラスの命名
IDとクラス名にはちゃんと意味のわかる名前を使うこと。
見た目を反映したものやそれが何を表しているか不可解な名前ではなく、要素の目的や役割を反映した名前を付ける。
