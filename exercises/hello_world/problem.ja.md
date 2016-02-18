まずは Express.js で、`/home` にアクセスすると `Hello World!`と出力するアプリを作ってみましょう。

ポート番号は、{appname} により、あなたの作成するアプリの第一引数として提供されます。
例: `process.argv[2]`.

演習を確認する前に、（Mac OS Xのターミナルで） `$ killall node`を実行し、以前のプロセスを終了しましょう。

Windowsの場合はコマンドプロンプト上で `taskkill /IM node.exe` です。

(もし未だなら) Express.js のインストールを忘れずに。
```
$ npm install express --save
```

-----------------------------

## ヒント

Express.js で、ポート番号3000をリッスンし、`'/'` にアクセスすると`Hello World!`と返すアプリはこう書きます。

```js
var express = require('express')
var app = express()
app.get('/', function(req, res) {
  res.end('Hello World!')
})
app.listen(3000)
```

あなたの回答では、ハードコードされたポート番号の代わりに `process.argv[2]` を使う様にしてください。

```js
app.listen(process.argv[2])
```

Videos: http://bit.ly/1jW1sBf.
