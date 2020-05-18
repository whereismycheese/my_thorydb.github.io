---
layout: post
title:  "filter()"
subtitle:   "-"
categories: jquery
tags: jquery
comments: true
header-img: img/jquery/filter.jpg
---
`$(selector).filter(criteria,function(index))`

:point_right:The `filter() method` is the opposite of the `not() method`.  
:point_right:이것들 중에서(group element) 내가원하는 이러한 특징(criteria)을 가진 element만 필터링

<br><br>
```javascript
$("p").filter(".intro")
```
