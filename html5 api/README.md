# HTML5 6 節

## 小畫家簽名

利用 canvas 實作

### 0517 1 節

沒做筆記

### 0518 2 節

- html5 selection
  - selectId.selectedIndex
  - selectId.value
  - selectId.selectedOptions //HTMLCollection
- html output tag
- input 屬性 pattern="正規表達式"

```js
[0-9] 範圍
^ 開頭
$ 尾部
\d 所有數字
{長度}
```

---

### 0519 1 節

- 表單驗證
  - el.checkValidity()
  - elid.validity //驗證屬性
  - elid.validity.misMatch //true==不通過
  - pattern 不輸入不會檢查|輸入一定檢查
  - elid.setCustomValidity()
  - elid.reportValidity()

---

- 影片 `<video>`

```html
<video width="320" height="240" controls class="video" crossorigin="anonymous">
  <source src="a.mp4" type="video/mp4" />
  <track src="a.vtt" kind="subtitles" label="English" />
</video>
<button onclick="console.log(video.paused)">print</button>
<button onclick="console.log(video.play())">start</button>
<button onclick="console.log(video.pause())">pause</button>
<script>
  var video = document.querySelector(".video");
  video.onloadstart = function () {
    var tracks = video.textTracks[0];
    tracks.mode = "showing";
  };
</script>
```

- 可以加入字幕檔案(格式如下)

```txt
WEBVTT

1
00:00:00.000 --> 00:00:10.000
Man did you see that awesome thing like last week -

2
00:00:10.000 --> 00:00:16.000
- and i said wow a lot of people are starting to talk about this.
```

影片播放/暫停
禁音/取消
時間軸
全螢幕/取消
影片字幕

icon 小組討論

---

## 0520 2 節

1. drag & drop
2. localStorage / Session / cookie
3. class constructor #private get set

依據條件指定物件屬性（conditionally assign object key）

```js
let person = {
  firstName: "Aaron",
  lastName: "Chen",
  greet: function () {
    console.log(`${this.firstName} ${this.lastName}`);
  },
};

let john = Object.create(person); // John 會繼承 person 這個物件
```
