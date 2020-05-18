---
layout: post
title:  "each method"
subtitle:   "-"
categories: jquery
tags: jquery
comments: true
header-img: img/jquery/each.jpg
---
`$(selector).each( function )`

:point_right:하나하나 각각의 선택된 element들에게.. 명령한다

Iterate over a jQuery object, executing a function for each matched element.
<br><br>
```html
<ul>
  <li>foo</li>
  <li>bar</li>
</ul>
```

```javascript
$( "li" ).each(function( index ) {
  console.log( index + ": " + $( this ).text() );
});
```
