# XHLHttpRequest 前端

## From架構
一般From 可透過submit傳送給後端
<form action="/search" method="get">
    <input type="text" name="name" placeholder="name">
    <input type="text" name="age" placeholder="age">
    <input type="submit" value="Submit">
</form>

##



##  XHLHttpRequest範例
### html部分
<p>XHLHttpRequest 可透過按鈕傳輸</p>
<form action="/search" method="get">
    <input id="xml_name" type="text" name="name" placeholder="name">
    <input id="xml_age"  type="text" name="age"  placeholder="age">
    <input type="submit" value="XHLHttpRequest">
</form>

```html
<form action="/search" method="get">
    <input id="xml_name" type="text" name="name" placeholder="name">
    <input id="xml_age"  type="text" name="age"  placeholder="age">
    <input type="submit" value="XHLHttpRequest">
</form>
```


### js部分
抓取name 和 age 和 button 的值
從 docuemnt(網頁文件)的getelementbyid 抓 ID; 
```js
const name_input = document.getElementById("name_input");
const age_input  = document.getElementById("age_input");
const btn_input  = document.getElementById("btn_input");
```


```js
btn_input.addEventListener("click", () => {
    console.log("btn_input click: name_input:", name_input.value, ", age_input:", age_input.value);

    let xhr = new XMLHttpRequest();
    let url = "/search?name=" + name_input.value + "&age=" + age_input.value;
    console.log("url: " + url);
 
    xhr.open("GET", url);
    xhr.timeout = 5000;
    xhr.send();

    xhr.onreadystatechange = () => {
        if (xhr.readyState === 4 && xhr.status === 200) {
            console.log("xhr.responseText: " + xhr.responseText);
        }
    };
});

```
詳細講解:

當按鈕被按下時做接下來的動作， addEventListener 監聽， click 點擊
```js
btn_input.addEventListener("click", () => { });
```
設定 XMLHttpRequest 為 xhr
```js
let xhr = new XMLHttpRequest();
```

設定 url
```js
 let url = "/search?name=" + name_input.value + "&age=" + age_input.value;
```
列出url，舉例 `http://localhost:3000/search?name=name_input&age=age_input.value`
```js
 console.log("url: " + url);
```
連線設定使用GET
```js
 xhr.open("GET", url);
```
連線時間設定5秒，1000 = 1秒
```js
 xhr.timeout = 5000;
```

送出
```js
 xhr.send();
```

當傳送之後 來進行裡面的動作  onreadystatechange = 當請求被發送到服務器時
```js
xhr.addEventListener('onreadystatechange', () => { });
```

當傳送的 state 數值為 `4` 和網頁狀態為 `200` 就顯示回傳的數值
```js 
if (xhr.readyState === 4 && xhr.status === 200) {
    console.log("xhr.responseText: " + xhr.responseText);
}
```


 












