## 你會嗎?

### 0506
`事件冒泡`
function 觸發複習?

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

`event.preventDefault`
`event.stopPropagation`
js 限制使用者 輸入小寫

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

原來id可以直接當變數用 不用宣告...
imid.click = function(){console.log(123)}
js經典 事件冒泡(傳導)，阻止

### 0509
### 0510

### 0511

```js

1A2B 寫程式的邏輯
早上檢討作業
jQuery filter回傳機制

    <script>
        $('li').filter(function (i, el) {
            if(el.innerText === '草莓') return true;
        }).each(function(c, d){
            console.log(d); // 草莓
        })
    </script>

$('li').eq(0) //li很多個 選第一個

### 0512
昨天寫到 HSL變換顏色的HW
sec = (first+180)%360

學了
toggleClass() //若多包一層function則失效
addClass()
removeClass()//預設是全部消除

`on('事件名稱',方法)`
- click
- mouseover
`多事件合併`

`分清楚四組XY座標`
```