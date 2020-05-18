---
layout: post
title:  "call() 2"
subtitle:   "this is subtitle for call()"
categories: javascript
tags: javascript web-dev
comments: true
header-img: img/javascript/js_call.jpg
---

>Javascript Function Call()  

:point_right: `특정함수이름.call(this);` 여기서 this는?

<br>
```javascript
function redLineFn() {

  $(this).addClass("trLine");
  //여기서 this는 $("tbody:eq(0) > tr")
}
```
```javascript
$("tbody:eq(0) > tr").each(function(index, value) {

  if (inputVal === $(this).children("td:eq(2)").text()) {
    // red line css 적용
    redLineFn.call(this); //여기서 this는 $("tbody:eq(0) > tr")
  }
}); //each
```
