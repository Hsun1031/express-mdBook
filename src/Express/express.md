# Express

Expree 基本架構

```js
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => res.send('Hello World!'));

app.listen(port, () => console.log(`Example app listening on port ${port}!`));
```

導入 express 模組。

```js
const express = require('express');
```

初始化 express，並存入 app 變數。

```js
const app = express();
```

設定 port。連入伺服器的網址為 `http://localhost:3000`。

```js
const port = 3000;
```

## get

設定路由，當使用者連入 `http://localhost:3000/` 時，會執行 callback function。

```js
app.get('/', (req, res) => res.send('Hello World!'));
```
這個函式傳入了2個參數
1. `'/'` 為 路徑，因此 http://localhost:3000`/` 的最後面有 `/`。
2. `(req, res) => res.send('Hello World!')` 為 callback `function`，當使用者連入 `http://localhost:3000/` 時，會執行 callback function。
  - `req` 為 request 的縮寫，指客戶端(client)`傳入`伺服端(Server)的資料。
  - `res` 為 response 的縮寫，指伺服端(Server)`回傳`給客戶端(client)的資料。

因此代表
```js
app.get(<傳入路徑>, <函式>);
```

### app.get 不同寫法

最多人用法

```js
app.get('/', (req, res) => {
    res.send('Hello World!');
});
```

當只有一行時，可以省略 `{}`

```js
app.get('/', (req, res) => res.send('Hello World!'););
```

如果不同路徑使用相同函式，可以使用函式

```js
app.get('/', hello);
app.get('/hello', hello);

function hello(req, res) {
    res.send('Hello World!');
}
```

舊的用法

```js
app.get('/', function(req, res) {
    res.send('Hello World!');
});
```

## listen
起始伺服器，並監聽 port。

```js
app.listen(port, () => console.log(`Example app listening on port ${port}!`));
```
