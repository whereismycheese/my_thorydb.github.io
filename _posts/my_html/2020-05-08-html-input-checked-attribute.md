---
layout: post
title:  "input checked attribute"
subtitle:   "-"
categories: html
tags: html
comments: true
header-img: img/html/input.jpg
---
>HTML <input type="checkbox" checked> checked Attribute

:point_right: The `checked` attribute is `a boolean attribute`.  
:point_right: html요소의 속성으로 `checked라고 이름`이 들어가면 True, 이름이 없으면 False

The checked attribute can be used with `<input type="checkbox">` and `<input type="radio">`.  
The checked attribute can also be set after the page load, with a JavaScript.  
<br><br>
```html
<table>
  <thead>
    <th><input type="checkbox" name="headChk" onclick="totChkFn();" /></th>
  </thead>
  <tbody>
    <tr>
      <td><input type="checkbox" name="bodyChk" checked/></td>
      <!-- 이 체크박스만 체크된 상태로 브라우저에 로딩된다 -->
    </tr>
    <tr>
      <td><input type="checkbox" name="bodyChk" /></td>
    </tr>
    <tr>
      <td><input type="checkbox" name="bodyChk" /></td>
    </tr>
  </tbody>
</table>
```

```javascript
function totChkFn() {
  //모든 바디에 있는 체크박스를 잡는다
  var $bodyChk = $("input[name='bodyChk']");

  //전체체크 누르면 -> 모든 체크박스 체크되도록
  if($("input[name='headChk']").is(":checked")) {
    $bodyChk.prop("checked", true);
  }else {
    $bodyChk.prop("checked", false);
  }
}
```
