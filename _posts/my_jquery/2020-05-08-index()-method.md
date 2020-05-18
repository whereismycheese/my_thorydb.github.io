---
layout: post
title:  "index()"
subtitle:   "-"
categories: jquery
tags: jquery
comments: true
header-img: img/jquery/index.jpg
---
`$(selector).index()`

:point_right: 형제 element들 중에서 너는 몇번째?  
:point_right: If the element is not found, index() will `return -1`.

the index position of specified elements relative to other specified elements.  
<br><br>
```html
<p>Click the list items to get the index position, relative to its sibling elements</p>

<ul>
  <li>Coffee</li>
  <li>Milk</li>
  <li>Soda</li>
</ul>

```

```javascript
$(document).ready(function(){
  $("li").click(function(){
    alert($(this).index());
  });
});
```
