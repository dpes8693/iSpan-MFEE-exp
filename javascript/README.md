## JS 12 節

### 0401 2 節

- 以車子為例，它有哪些方法&屬性?
- `null`| `0`| `''`| `undefined`| `' '`，這五個有什麼差異?
- ` BOM``DOM `分別是甚麼?
- `js`在`html`位置有差異?為什麼沒有反應?
- `var` `let` `const` 差異?
- `hoisting` 是什麼意思?
- `<script src="test.js">console.log(123)</script>`為什麼沒有印出 123?
- `console.time()` `console.timeEnd()` 有什麼作用?
- `console.group()` `console.groupEnd()` 有什麼作用?
- `<script defer src="test.js"></script>` `defer`有什麼作用?

### 0406 2 節

- VScode 內建方法怎麼看參數?
- String 方法
  - str.length
  - slice()
  - indexOf()
  - lastIndexOf()
- 比較 substr()、substring()、slice()
- NaN、Infinity、-Infinity 差異是?
- Number 方法
  - toFixed(2) toPrecision(2) 差異是?
  - num.toString()
  - 0.1+0.2!=0.3
- Array 方法
  - push() unshift()
  - pop() shift()
  - 0.1+0.2!=0.3
- Object 簡介

### 0407 2 節

- Operator
  - `++a` `a++` 差異是?請以判斷式舉例。
  - `console.log(3>2>1)`為什麼印出`false`?
  - 請寫出`Ternary Operator`
- Math()
  - PI
  - random()
  - ceil() floor()
  - round()
  - sqrt()
  - abs()
- Date()
  - setDate() getDate()
  - `let d = new Date()`
  - 很多方法
  - 最後一天怎麼找?

### 0408 2 節

- window
  - alert()
  - prompt()
  - confirm()
  - confirm()
- 計時器
  - setInterval()//handler 就是塞入 function
  - setTimeout()
  - clearInterval()
  - clearTimeout()
- DOM 操作
  - byId
  - byTagName
  - querySelector
- getPropertyValue
- 為什麼 el.style.top 是空的，我在 CSS 有設定?
- 補充日期方法
- d.toLocaleString() //2022/4/8 上午 11:17:42
- d.toLocaleDateString() //2022/4/8
- 如何抓取 CSS style,inlineStyle

  - getElementsByTagName
  - getElementsByClassName
  - getElementById
  - querySelector
  - querySelectorAll

- dom style 分兩種
  - getComputedStyle(el).getPropertyValue()
  - window.getComputedStyle()

```js
const el = document.getElementById("t");
let cssStyle = getComputedStyle(el);
let inStyle = el.style;
console.log(cssStyle);
console.log(inStyle);
console.log(cssStyle.getPropertyValue("color"));
console.log(inStyle.getPropertyValue("color"));
```

### 0411 2 節

- 如何用 JS 抓到 DOM 的 element?
- 呈上 如何抓到 element 的 CSS?
- 如何實作點 btn 讓網頁上的文字和圖片放大?
- 小專題說明
- add element
  - createElement()
  - createTextNode()
  - setAttribute()
  - insertBefore()
- parseInt() toFixed() 差異是?
- 有設定 CSS 為什麼 el.style.height 是空值?
- scroll reveal 怎麼做?
- switch case default
- while do while

### 0412 2 節

- alert prompt
- str.trim()
- for break continue
- for(;;) 特殊狀況
- 用迴圈印出三角形，九九乘法表
- for in for of
- function return
- ES6 箭頭函數
- 參數 引數 差異?
- this 關鍵字(window, el-event, obj)
- null，會傳成 object

```js
  var d = [];
  console.log(typeof d); // object
  console.log(Object.prototype.toString.call(d)); // [object Array]
```



## closure 範例

```js
        //closure
        for (var i = 0; i < 3; i++) {
            setTimeout(function () { console.log(i) }, 1000);
        }
        //進化
        for (var i = 0; i < 3; i++) {
            (function (j) {
                //function scope
                setTimeout(function () { console.log(j) })
            }(i)) // 把i傳進去這個閉包
        }
        //進化
        for (var i = 0; i < 3; i++) {
            a(i) // 把i傳進去這個閉包
        }
        function a(j) {
            setTimeout(function () { console.log(j) })
        }
        //問號
        (function function1() {
            var t = 10;

            (function function2() {
                g = 20;
            }())

        }())
        console.log(g)
        console.log(t) //Reference Error
```

## this

[https://www.w3schools.com/js/js_this.asp](https://www.w3schools.com/js/js_this.asp)

- this 居然可以用在 html 透過 onclick(傳遞)!!

```js
        // 10. Alone, this refers to the global object.
        // 20. In a method, this refers to the owner object.
        // 30. In an event, this refers to the element that received the event.
```

先記住三個規則

- window
- onclick 事件 => element
- obj
