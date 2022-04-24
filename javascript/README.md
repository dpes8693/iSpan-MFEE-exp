## 你會嗎?

### 0401 2 節

- 以車子為例，它有哪些方法&屬性?
- `null`| `0`| `''`| `undefined`| `' '`，這五個有什麼差異?
- `BOM``DOM`分別是甚麼?
- `js`在`html`位置有差異?為什麼沒有反應?
- `var` `let` `const` 差異?
- `hoisting` 是什麼意思?
- `<script src="test.js">console.log(123)</script>`為什麼沒有印出123?
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
    - setInterval()//handler 就是塞入function
    - setTimeout()
    - clearInterval()
    - clearTimeout()
- DOM操作
    - byId
    - byTagName
    - querySelector
- getPropertyValue
- 為什麼 el.style.top是空的，我在CSS有設定?
- 補充日期方法
    - d.toLocaleString() //2022/4/8 上午11:17:42
    - d.toLocaleDateString() //2022/4/8
-如何抓取CSS style,inlineStyle
    getElementsByTagName
    getElementsByClassName
    getElementById
    querySelector
    querySelectorAll

==getComputedStyle(el).getPropertyValue()==
window.getComputedStyle()
    
dom style分兩種
const el = document.getElementById('t')
let cssStyle = getComputedStyle(el)
let inStyle = el.style
console.log(cssStyle)
console.log(inStyle)
console.log(cssStyle.getPropertyValue('color'))
console.log(inStyle.getPropertyValue('color'))

### 0411 2 節
- 如何用JS抓到DOM的element?
- 呈上 如何抓到element 的CSS?
- 如何實作點btn讓網頁上的文字和圖片放大?
- 小專題說明
- add element
    - createElement()
    - createTextNode()
    - setAttribute()
    - insertBefore()
- parseInt() toFixed() 差異是?
- 有設定CSS為什麼el.style.height是空值?
- scroll reveal怎麼做?
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
- this關鍵字(window, el-event, obj)
null，會傳成object

  var d = [];
  console.log(typeof d);  //  object
  console.log(Object.prototype.toString.call(d)); //  [object Array]

shift + delete
log
往下拉


<!-- ### 想法 -->

<!-- 魔王教你JS資料操作
變數,陣列,物件?

要如何擊敗勇者隊伍呢? 魔王軍隊陣行不好安排...
史萊姆 哥布林 骷髏士兵 地獄犬

攻擊方式: 單體/群體
攻擊順序排序: 有/無

let 先發 = '史萊姆' //單體無排序
let 中鋒 = ['史萊姆','骷髏士兵'] //群體有排序
let 總攻擊 = {left:'地獄犬',right:'哥布林'} //群體無排序
let 長征隊伍 = [
    {left:'地獄犬',right:'哥布林'},
    {left:'史萊姆',right:'骷髏士兵'},
    {left:'史萊姆',right:'史萊姆'}
] //群體有排序=>群體無排序
let 混合型 = {
    alpha: '史萊姆',
    beta: ['史萊姆','骷髏士兵'] ,
    gamma: {left:'地獄犬',right:'哥布林'}
} -->

## 採坑日誌

```js
//no error msg
0.1+0.2 != 0.3 //0.30000000000000004
hoisting
閉包
拷貝 記憶體位置
string 無法更改char str[1]='a'
typeof
setInterval( function()直接執行){}
隱轉
同步 非同步
大數字，小數點
this
字母排序 [1,2,5,10].sort() //文字排序
d.getMonth()+1 //0-11
NaN 不能比較
alert prompt console 順序


不正常
for(;;)
for(a();false;b()) //b()不會執行
for ( var i = 0 ; i < 3 ; i++ ) {
	setTimeout( function() { console.log(i) } , 1000 );
}// 3 3 3
```
https://keep.google.com/u/0/#home


## 
this可以用在html 透過onclick(傳遞)!!

        // 10. Alone, this refers to the global object.
        // 20. In a method, this refers to the owner object.
        // 30. In an event, this refers to the element that received the event.

-window
-onclick事件 => element
-obj
-https://www.w3schools.com/js/js_this.asp