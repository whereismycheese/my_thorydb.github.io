---
layout: post
title:  "null check"
subtitle:   "-"
categories: javascript
tags: javascript web-dev
comments: true
header-img: img/javascript/null.jpg
---

> null? [here](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/null)  

JavaScript의 원시 값 중 하나로  
어떤 값이 의도적으로 비어있음을 표현  
불리언 연산에서는 거짓으로 취급  

```javascript
// 정의되지 않고 초기화된 적도 없는 foo
foo; //ReferenceError: foo is not defined

// 존재하지만 값이나 자료형이 존재하지 않는 foo
var foo = null;
foo; //null
```
<br>
> null check WHY?  

![why_null_chk](/assets/img/javascript/why_null_chk.png)  

cookie에 아직 아무런 값이 저장되지 않은 상황인데..  
즉, cookie에는 현재 null값이 들어있는 상황..  
코드상 null에 split()메서드가 적용되는 상황이 되버린다!  
<br>
> null check을 하는 방법?  

![check_null_how](/assets/img/javascript/check_null_how.png)  
