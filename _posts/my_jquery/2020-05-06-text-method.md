---
layout: post
title:  "text method"
subtitle:   "-"
categories: jquery
tags: jquery
comments: true
header-img: img/jquery/text.jpg
---

`$(selector).text()`

`$(selector).text(content)`

`$(selector).text(function(index,currentcontent))`

:point_right: html의 요소가 가진 text content(html태그는 제외함)를 get or set  
:point_right: html태그 + text content 모두 가져오려면 html() method 사용  
:point_right: jquery val() method와 비교!  

sets or returns the `text content` of the selected elements.
<br><br>
```html
<p>Name: <input type="text" name="user"></p>
<button>Set the value of the input field</button>
```

```javascript
$(document).ready(function(){
  $("button").click(function(){
    $("input:text").val("Glenn Quagmire");
  });
});
```
