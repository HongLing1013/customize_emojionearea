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

## 自定義emoji

- 使用 before 的方式，讓圖片可顯示在 Emoji 面板區域

```js
events: {
    ready: function () {
        $('.emojionearea-category[name="recent"]').before(
            '<div class="emojionearea-category" name="區塊名稱" data-tone="0">'+
                '<div class="emojionearea-category-title">區塊標題 1</div>'+
                '<i class="emojibtn" role="button" data-name=":圖案名稱 1:" title="圖案標題 1">'+
                    '<img class="emojioneemoji" src="圖片路徑 1">'+
                '</i>'+
                '<div class="emojionearea-category-title">區塊標題 2</div>'+
                '<i class="emojibtn" role="button" data-name=":圖案名稱 2:" title="圖案標題 2">'+
                    '<img class="emojioneemoji" src="圖片路徑 2">'+
                '</i>'+
            '</div>');
        $('.emojionearea-category[name="區塊名稱"] i').each(function () {
            $(this).on('click', function() {
                pasteHtmlAtCaret('<img alt="'+$(this).data("name")+'" class="emojioneemoji" src="'+$(this).find('img').attr("src")+'">');
            });
        });
    }
}
```

- 為了點擊圖示時可順利將圖示加入輸入框，要將套件中的 pasteHtmlAtCaret 的 function 複製一份