フォームは重要です。この演習では、従来のWebフォーム（非Ajax）を処理する方法をお教えします。

HTML入力フォーム (`<form><input name="str"/></form>`) を返す route (`'/form'`) を書いてください。そして、`str`の値を返す様にしてください。

POSTリクエストを処理するには、`get()` と同様に`post()`メソッドを使用します。

```js
app.post('/path', function(req, res){...})
```

Express.jsは、あなたのWebサーバーの機能を拡張する手段として、`ミドルウェア（middleware）`という仕組みを使用します。

ミドルウェアとは、簡単に言えば、あなた独自のリクエストハンドラの前にExpressjsによって呼び出される関数です。

ミドルウェアは、ロギング、静的ファイルの提供、エラー制御など、多種多様な機能を提供します。

アプリケーション内で`use()`を使い、そのパラメータにミドルウェアを渡すことによって、アプリケーションにミドルウェアが追加されます。

A middleware is added by calling `use()` on the application and passing the middleware as a parameter.

`ののx-フォームurlencoded` WWW要求体を解析するには、Expressjsは`ボディparser`モジュールから`URLエンコード（）`ミドルウェアを使用することができます。
To parse `x-www-form-urlencoded` request bodies, Express.js can use `urlencoded()` middleware from the `body-parser` module.

```js
var bodyparser = require('body-parser')
app.use(bodyparser.urlencoded({extended: false}))
```


-----------------------------

## HINTS

Here is how we can print characters backwards (just one way to do it):

```js
req.body.str.split('').reverse().join('')
```

Extended set to true (qs) or false (querystring) determines the parser module.

Read more about Connect middleware here:

  https://github.com/senchalabs/connect#middleware

The documentation of the body-parser module can be found here:

  https://github.com/expressjs/body-parser

Videos: http://bit.ly/1jW1sBf.

-----------------------------

## NOTE

When creating your projects from scratch, install the `body-parser` dependency
with npm by running:

```sh
$ npm install body-parser
```

…in your terminal.

Again, the port to use is passed {appname} to the application as `process.argv[2]`.
