---
layout: post
title:  "tree traversal methods"
subtitle:   "-"
categories: jquery
tags: jquery traversal selectors
comments: true
header-img: img/jquery/tree.jpg
---

:point_right: 시작요소부터 시작해서 원하는 요소를 찾아내기 위한 여행traversing  
:point_right: 그럼 [시작요소](/jquery/selectors/2020/05/06/selectors.html)는 어떻게 찾아?

| 요소찾기 method :evergreen_tree: | 누구를 찾는가  | example code |
| ------------- |:-------------:|:-----:|
| 시작요소.children() | 바로 아래 children | `$("ul").children().css({"color": "red", "border": "2px solid red"});` |
| 시작요소.find(찾는요소) | 해당 children 모두 | `$("ul").find("span").css({"color": "red", "border": "2px solid red"});` |
| 시작요소.closest(찾는요소) | 해당 가장가까운 ancestor | `$("span").closest("ul").css({"color": "red", "border": "2px solid red"});` |
| 시작요소.parent() | 바로 위 ancestor | `$("span").parent().css({"color": "red", "border": "2px solid red"});` |
| 시작요소.parents() | 위에위에 ancestor들까지도 | `$("span").parents().css({"color": "red", "border": "2px solid red"});` |  
| 시작요소.next() | 바로 옆에 나타난 sibling | `$("li.start").next().css({"color": "red", "border": "2px solid red"});` |
| 시작요소.nextAll() | 이후 나타난 sibling모두 | `$("li.start").nextAll().css({"color": "red", "border": "2px solid red"});` |
| 시작요소.prev() | 바로 이전 sibling | `$("li.start").prev().css({"color": "red", "border": "2px solid red"});` |
| 시작요소.siblings() | 위아래 모든 siblings | `$("li.start").siblings().css({"color": "red", "border": "2px solid red"});` |
