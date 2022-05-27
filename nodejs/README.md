## 0527 2
Nodejs是什麼?
如何安裝Nodejs?
如何在電腦(本機)執行js檔案
觀念 請求如果找到就返回了
get
use

### module
var http = require('http')//麻煩 後來被包進express
querystring
qs
query-string
body-parser
    URLSearchParams API

HTTP Server模組教學 
//require('http')
//http.createServer(function(req, res){ //處理請求 })
//非同步函數 


express.Router()
app.use(function(){...})
res.send('Express is fun!')
res.json({})
app.use(express.static('files'))
var fs = require("fs"); //file system
```js
var express = require('express');
var app = express();

app.get('/', function (req, res) {
  res.send('Express is fun!');
});

var router = express.Router();

router.get('/data', function (req, res) {
  res.json({
    name: '財團法人資訊工業策進會',
    website: 'https://www.iii.org.tw/',
    address: '台北市大安區和平東路二段106號11樓',
    tel: '02-6631-8168'
  });
});

app.use('/', router);

app.listen(4000, function () {
  console.log('Example app listening on port 4000!');
});

```