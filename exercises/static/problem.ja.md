この演習では、HTMLファイルのような静的ファイルの表示について学びます。

色々な方法がありますが、ここでは`static`というミドルウェアを使って、`index.html`を表示させます。

`app.get`の様な route を使わないでください。静的ファイル限定です。(routeって何？という人、今は気にしないでください)

回答は、`process.argv[2]` で指定されたポート番号を使用する必要があります。

`index.html` のファイルパスは引数 `process.argv[3]` で供給されます。
あるいは、下記のファイルをあなた自身が作成し、回答に使用する事も出来ます。（その場合はスペースの数などに注意の事）

```html
<html>
  <head>
    <title>expressworks</title>
    <link rel="stylesheet" type="text/css" href="/main.css"/>
  </head>
  <body>
    <p>I am red!</p>
  </body>
</html>
```

-----------------------------

## HINTS

staticミドルウェアの使い方はこう:

```js
app.use(express.static(path.join(__dirname, 'public')))
```

{appname} が供給する引数（ファイルパス）を回答内で使うには:

```js
app.use(express.static(process.argv[3] || path.join(__dirname, 'public')))
```

Videos: http://bit.ly/1jW1sBf.
