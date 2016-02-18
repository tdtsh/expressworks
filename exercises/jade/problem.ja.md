Express.jsで、テンプレートエンジン`"jade"`で描画されるホームページを作成します。

ホームページは `/home` でアクセスできる必要があります。

ビューでは、`'new Date.toDateString()'`を使用して、現在の日付を表示する必要があります。

'toDateString()'は、人間が読める形式でシンプルに日付文字列（時刻を含まない）を返します。

-----------------------------

## HINTS

Jade テンプレートファイル `index.jade` はこうです:

```jade
h1 Hello World
p Today is #{date}.
```

あなたは私たちが提供する`index.jade`を使用することができます。（推奨） 
`index.jade` のファイルパスは引数 `process.argv[3]` で供給されます。

もちろん、あなた自身でのjadeファイルを作成し使用しても構いません。その場合はファイルの内容が私たちのものとまったく同じである事をよく確認してください。

`templates`フォルダ内のテンプレートファイルへのパスを指定する方法はこうです。

```js
app.set('views', path.join(__dirname, 'templates'))
```

`__dirname`は、（実行中の）ファイルへの絶対パスです。
path.joinは、プラットフォーム間（Windows、Linux、OSX等）のパスの相違を吸収するために使用します。

Express.jsで作成するアプリに、どのテンプレートエンジンを使用するかを教えるには、こうします。

```js
app.set('view engine', 'jade')
```

ハローワールドの回答内の `res.end()`の代わりに、`res.render()` 関数を使います。`res.render()` は引数として、テンプレートファイル名とデータ（localと呼ばれます）を受け付けます。

```js
res.render('index', {date: new Date().toDateString()})
```

人間が読める形式でシンプルな日付（時刻を含まない）を返すのに、`toDateString()`を使用します。

--------------------------------

## NOTE

最初からプロジェクトを作成する場合は、npmで`jade`とその依存関係をインストールします。

このパッケージ（expressworks）上で`$ npm install` を実行すると、jadeがインストールされます。

ここでも、{appname} が使用するポートは`process.argv[2]`として提供されます。

エラーメッセージ：`Error: Cannot find module 'jade'` を受け取った場合、Express.jsがその相対パス上に jade を探している（そして見つけられない）事が原因です。 

`npm install jade` を実行することでこの問題を解決することができます。

Videos: http://bit.ly/1jW1sBf.
