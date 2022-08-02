# PHP 12 節

> 教太多了學不完XD


- PHP 語法

  - `<?php ... ?>`
  - echo
  - print_r($arr)
  - var_dump()
  - prinf
  - unset($x);
  - isset($\_POST["name"])
  - 字串可以比較(和 JS 不同)
  - gettype() 取型態
  - substr($x,'1','2'); 切
  - str_replace('0','9',$x); 取代
  - strpos($x,'23'); 找位置
  - strlen() 長度
  - iconv('UTF-8','big5',$x) 轉換編碼
  - strtr("Hilla Warld","ia","eo") 替換
  - strtok() split
  - foreach($arr as $value)
  - sort()
  - natsort() 自然排序;數字由小到大
  - usort()

- Type

  - String $x = “abc”
  - Number $x = 4
  - TimeStamp $x = strtotime(gmdate(“Y-m-d H:i:s”));
  - Boolean $x = true
  - MultiLines <<<
  - 相加用點 $a . $b

- OOP
  - function \_\_construct()
  - function \_\_destruct()
  - function \_\_get($key,$value)
  - function \_\_set($key,$value)
  - get_class_vars("Animal") //array
  - unset()
  - E_USER_ERROR
  - php extends
  - interface
  - instance

```php
<?php
// 預設是public
class Animal{
    public $weight;
    public function makeSound($weight){
        echo $weight;
    }
}
?>
```

- 時間

  - $d = mktime(11,59,59, 4,22,1999)
  - date()

- IO

  - feof
  - file() Array
  - file_get_contents() string
    - fopen()
    - fgets()
    - fclose()
    -
    - fopen()
    - fread() bytes
    - fclose()
  - file_put_contents() string
    - fopen()
    - fputs()
    - fclose()
    -
    - fopen()
    - fwrite() bytes
    - fclose()

- 套件

  - cURL
  - curl_setopt

- VScode 輔助套件
  - PHP Server

## 作業: 正規化

[正規化](https://www.figma.com/file/PC6xkD8eRdKajHkMHJfVUf/%E8%B3%87%E6%96%99%E5%BA%AB%E8%A8%AD%E8%A8%88HW?node-id=0%3A1)

## 補充

- setopt = set option 縮寫
- curlopt= cURL option 縮寫
- windows CMD 是 Big5

- big5 vs UTF8
  - 前者中文 2Byte 後者 3Byte

```php
// 怎麼寫出 錯誤發生繼續跑完的程式
<?php
	for($i = 1; $i <= 9; $i++) {
	   $errorCount = sendMail($i);
	   if ($errorCount > 10000) {
			break;
	   }
	   if ($errorCount > 0) {
		  sendMail($i);
	   }
	}
	function sendMail($i) {
		$err = 0;
		try {
			if ($i == 4)
				throw new Exception("An Error occured");
			echo $i . "<br>";
		}
		catch (Exception $ex) {
			echo "Error: $i<br>";
			$err += 1;
		}
		return $err;
	}
?>
```

---

未整理

## 0503 2 節

- php 如何連線 DB(語法是?)

  - $link = mysqli_connect("127.0.0.1","root","",$db,$port) or die(mysqli_connect_error());

- 方法
  - mysqli_close
  - mysqli_connect
  - mysqli_connect_error
  - mysqli_fetch_assoc
  - mysqli_query
  - mysqli_select_db
  - mysqli_connect_errno

- beginTransaction
- errorCode
- commit
- rollBack
- errorInfo

- new PDO
- new stdClass
- new App
- new DOMXPath
- new DOMDocument

- execute()
- fetch()
- fetchObject
- getMessage

- setAttribute
- bindParam
- prepare
- libxml_use_internal_errors
- loadHTML

- curl_init
- curl_setopt
- curl_exec
- curl_close

![概念圖](https://i.imgur.com/cpll48K.png)

![show variables](https://i.imgur.com/eAPzboH.png)

php 摸熟後 select 怎麼撈

![](https://i.imgur.com/WvH5oU2.png)

lock in share mode

[PDO 教學](https://blog.markgdi.com/article/quick-start-operation-mysql-using-php-pdo/)

## 0504 2節

![last end](https://i.imgur.com/2skBV64.png)

```php=

//----------------------------PDO
//begnTransaction()
//rollBack()
//https://phpdelusions.net/pdo_examples/select


query("select * from students")//沒參數 要查詢
 exec("set names utf8")//沒參數 沒查詢

//有參數
new PDO //生成 並連線
prepare() //阻止SQL Injection//準備
bindValue() //變數綁上去
execute() //執行

errorCode() 00000 成功
!= 成功 的話 throw  new Exception("test test test");

$sth = $dbh->prepare("SELECT name, colour FROM fruit");
$sth->execute();
$result = $sth->fetchAll();
print_r($result);

---------------------------File
dirname() //選資料夾
opendir() //連線
readdir() //讀取
closedir() //離開

&lt; less then
&gt; greater then
&nbsp; no-break space
----------------------html
$line = file('data.text')
htmlspecialchars($line) //阻止SQL Injection //<被轉換
----------------------txt f
$contents = file_get_contents('data.text')
str_replace("\r\n","<br/>",$contents)


$content = <<<fileContent
..x.x...
fileContent;

$fileSize = file_put_contents("data2.txt",$content)//選對象 更改成
file() //array
feof()逐列掃描
fopen()
fgets()逐列獲取//減少記憶體 string
futs()
fclose()
Trim()

fread()
fwrite()

b binary啦 丟喜圖片
```

`原來可以 img src="picture.php" `

```php=
<?php
function gen_one_to_three() {
    for ($i = 1; $i <= 3; $i++) {
        //注意变量 $i 的值在不同的 yield 之间是保持传递的。
        echo "生成一个值 $i \n";
        //yield
        yield $i;//時間停止器
    }
}
function gen_one() {
    for ($i = 1; $i <= 3; $i++) {
        echo "生成一个值 $i \n";
        //return
        return $i;
    }
}

$generator = gen_one_to_three();
foreach ($generator as $value) {
    echo "$value\n"."<br>";
}
echo '<hr>';
$generator2 = gen_one();
echo $generator2."<br>";

```
