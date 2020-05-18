---
layout: post
title:  "val()"
subtitle:   "-"
categories: jquery
tags: jquery
comments: true
header-img: img/jquery/val.jpg
---
`$(selector).val()`

`$(selector).val(value)`

`$(selector).val(function(index,currentvalue))`

:point_right: form element의 값을 가져오고 싶을때

The val() method returns or sets the value attribute of the selected elements.  
get the values of `form elements` such as `input`, `select` and `textarea`.  
When called on an empty collection, it returns `undefined`.
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
