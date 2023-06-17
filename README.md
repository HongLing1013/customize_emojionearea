# customize_emojionearea

EmojiOneArea 是一個開源的JQuery的插件，他可以讓你在輸入框中輕鬆地插入使用 emoji 

https://github.com/mervick/emojionearea

## 安裝方式

官方提供的安裝方式有三種，而此範例用的是composer的方式

```composer require mervick/emojionearea ^3.0.0```

## 使用方式

把下面代碼加到 head 裡面，記得把 file/to/path/ 換成自己的檔案位置

```html
<link rel="stylesheet" href="file/to/path/css/emojionearea.min.css">
<script type="text/javascript" src="file/to/path/js/emojionearea.min.js"></script>
<script type="text/javascript" src="file/to/path/js/jquery.min.js"></script>
```

簡單的範例

```html
<textarea id="example1"></textarea>
<script type="text/javascript">
  $(document).ready(function() {
    $("#example1").emojioneArea();
  });
</script>
```