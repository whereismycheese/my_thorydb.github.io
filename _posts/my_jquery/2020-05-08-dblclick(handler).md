---
layout: post
title:  "dblclick(handler)"
subtitle:   "-"
categories: jquery
tags: jquery
comments: true
header-img: img/jquery/dblclick.jpg
---
`$(selector).dblclick(handler-function)`

:point_right:The dblclick event occurs when an element is double-clicked.  

<br><br>
```html
<p>Double-click on this paragraph.</p>
```

```javascript
$("p").dblclick(function(){
  alert("The paragraph was double-clicked.");
});
```
