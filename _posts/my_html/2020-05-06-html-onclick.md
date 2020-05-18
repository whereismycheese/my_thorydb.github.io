---
layout: post
title:  "onclick event"
subtitle:   "-"
categories: html
tags: html
comments: true
header-img: img/html/onclick.jpg
---
>HTML DOM EVENTS - onclick EVENT

`<element onclick="[JS FUNCTION NAME]">`
<br>
:point_right: element를 클릭하는 이벤트를 일으키면.. [JS FUNCTION NAME]함수가 실행된다!

The onclick event occurs when the user clicks on an element.
<br><br>
```html
<p id="demo" onclick="myFunction()">Click me.</p>
```

```javascript
function myFunction() {
  document.getElementById("demo").innerHTML = "YOU CLICKED ME!";
}
```
