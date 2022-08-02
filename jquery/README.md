# jQuery 12 節

### 0506 2 節

`事件冒泡`
function 觸發複習

```js
function f1(str) {
  console.log(str());
}
f1(function f() {
  return "hi~";
});
f1(() => "hi~~");
```

```js
function f2(str) {
  str("hi~~~");
}
f2(function f(str) {
  console.log(str);
});
f2((str) => console.log(str));
```

IIFE 是什麼? 請舉例

```js
var f = (function () {
  console.log(123);
})();
//進化
(function () {
  console.log(123);
})();
```

- `event.preventDefault`
- `event.stopPropagation`

- js 限制使用者 輸入小寫

```js
    <input type="text" id="textbox" onkeypress="check(event)" placeholder="pD">
    <input type="text" id="textbox" onkeyup="value=value.replace(/[^\a-\z]/g,'')">

    <script>
        function check(e) {
            let flag = 97 <= e.keyCode && e.keyCode <= 122
            if (!flag) e.preventDefault()
        }
        function lowerOnly(id) {
            let el = document.getElementById(id)
            el.value = el.value.replace(/[^\a-\z]/g, '')
        }

    </script>
```

- 原來 id 可以直接當變數用 不用宣告...
  - myId.click = function(){console.log(123)}
- js 經典 事件冒泡(傳導)，阻止

### 0509 2 節

未做筆記

### 0510 1 節

- 未做筆記
- 出作業用 JS 寫 1A2B

### 0511 2 節

- 早上檢討作業 撰寫 1A2B 寫程式的邏輯
- jQuery filter 回傳機制

```html
<script>
  $("li")
    .filter(function (i, el) {
      if (el.innerText === "草莓") return true;
    })
    .each(function (c, d) {
      console.log(d); // 草莓
    });
  //$('li').eq(0) //li很多個 選第一個
</script>
```

### 0512 2 節

- 昨天寫到 HSL 變換顏色的 HW

  - sec = (first+180)%360

- 學了 jQuery

  - toggleClass() //若多包一層 function 則失效
  - addClass()
  - removeClass()//預設是全部消除

- `on('事件名稱',方法)`

  - click
  - mouseover
  - `多事件合併`

- `分清楚四組XY座標`

### 0513 2 節

- jQuery 實戰
  - 旋轉圖片
  - 用 jQuery 將 JSON 資料 動態修改網頁資料 ex:魯夫人名
  - 實作 checkbox 全選

### 0516 1 節

- jQuery UI 教學
  - date picker

### 0517 1 節

- jQuery UI 教學
  - color slider picker
  - jQuery animate() //若需要控制 color 相關 CSS 需要外掛 UI

- jQuery UI 彈出效果
- light-box 套件 圖片燈箱

- 簡單帶過 HTML5 API
- API 是什麼
