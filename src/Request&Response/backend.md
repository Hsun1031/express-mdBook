# XHLHttpRequest 後端

## index.js 接收部分
```js
app.get('/search', (req, res) => { 
    console.log('[GET] http://localhost:3000/search');
    console.log(req.query);
    let name = req.query.name;
    let age  = req.query.age;

    let text = "HI, I am " + name + ", " + age + " years old.";
    res.send(text);
});
```

###  詳細介紹
req.query傳過來的數值存為變數 name 和 age 
```js 
 let name = req.query.name;
 let age  = req.query.age;
```
將 HI, I am " + name + ", " + age + " years old." 傳送到 /search 頁面
```js
 let text = "HI, I am " + name + ", " + age + " years old.";
 res.send(text);
```
舉例
`HI, I am ppp, I am 6 years old.`
##  新增同步套件 nodemon 
package.json 安裝 nodemon
```js 
"devDependencies": {
   "nodemon": "^3.0.1"
}
```
package.json 寫入debug 指令 `"debug": "nodemon index.js"`
```js
"scripts": {
  "start": "node index.js",
  "debug": "nodemon index.js"
}
```
執行可在cmd輸入
```shell 
 yarn debug 
```

