---
layout: post
title:  "selectors"
subtitle:   "-"
categories: jquery
tags: jquery selectors
comments: true
header-img: img/jquery/selectors.jpg
---

:point_right: `시작요소` 를 선택해서 이것저것 시키고 싶다!  
:point_right: 시작요소에서 시작해서 [tree관계](/jquery/tree-traversal/2020/05/06/tree-traversal-methods.html)에 따른 다른 요소를 찾는 방법?

:sparkles:몇번째인 특정요소를 찾는다  
:sparkles:누구의 이런자식을 찾는다  
:sparkles:이런특징을 가진 요소를 찾는다  
:sparkles:[이런attribute]을 가지거나 안가지거나 부분적으로 가진 요소를 찾는다  
:sparkles: 이런특징을 가진 input요소를 찾는다


| selectors | example code | :point_right:누구를 찾는가 |
| ------------- |:-------------:|:-------:|
| * | $("*") | All elements |
| #id | $("#lastname") | The element with id="lastname" |
| .class | $(".intro") | All elements with class="intro" |
|.class,.class|	$(".intro,.demo")| All elements with the class "intro" or "demo"|
|element|	$("p")	|All <p> elements|
|el1,el2,el3	|$("h1,div,p")|	All <h1>, <div> and <p> elements|
| :sparkles:몇번째인 특정요소를 찾는다 | |
|:first	|$("p:first")	|The first <p> element|
|:last|	$("p:last")	|The last <p> element|
|:even|	$("tr:even")|	All even <tr> elements|
|:odd	|$("tr:odd")|	All odd <tr> elements|
| :sparkles:누구의 이런자식을 찾는다| |
|parent > child	|$("div > p")	|All <p> elements that are a direct child of a <div> element|
|parent descendant|	$("div p")|	All <p> elements that are descendants of a <div> element|
| :sparkles:이런특징을 가진 요소를 찾는다 | |
|:eq(index)|	$("ul li:eq(3)")|	The fourth element in a list (index starts at 0) |
| :not(selector)|	$("input:not(:empty)")|	All input elements that are not empty|
| :contains(text)	|$(":contains('Hello')")|	All elements which contains the text "Hello"|
| :has(selector)|	$("div:has(p)")	|All <div> elements that have a <p> element|
|:hidden|	$("p:hidden")|	All hidden <p> elements |
| :visible|	$("table:visible")|	All visible tables|
| :sparkles:[이런 attribute]을 가지거나 안가지거나 부분적으로 가진 요소를 찾는다| |
|[attribute]|	$("[href]")	|All elements with a href attribute |
| [attribute=value]|	$("[href='default.htm']")	|All elements with a href attribute value equal to "default.htm"|
| [attribute!=value]|	$("[href!='default.htm']")|	All elements with a href attribute value not equal to "default.htm"|
| [attribute$=value]|	$("[href$='.jpg']")|	All elements with a href attribute value ending with ".jpg"|
| [attribute^=value]|	$("[title^='Tom']")	|All elements with a title attribute value starting with "Tom"|
| [attribute~=value]|	$("[title~='hello']")	|All elements with a title attribute value containing the specific word "hello"|
| [attribute*=value]|	$("[title*='hello']")	|All elements with a title attribute value containing the word "hello"|
|:sparkles: 이런 특징을 가진 input요소를 찾는다 | |
| :input|	$(":input")|	All input elements|
| :text|	$(":text")|	All input elements with type="text"|
| :password|	$(":password")|	All input elements with type="password"|
| :radio|	$(":radio")|	All input elements with type="radio"|
| :checkbox|	$(":checkbox")|	All input elements with type="checkbox"|
| :submit|	$(":submit")|	All input elements with type="submit"|
| :reset|	$(":reset")|	All input elements with type="reset"|
| :button	|$(":button")	|All input elements with type="button"|
| :image|	$(":image")|	All input elements with type="image"|
| :file	|$(":file")	|All input elements with type="file"|
| :enabled|	$(":enabled")|	All enabled input elements|
| :disabled	|$(":disabled")	|All disabled input elements|
| :selected|	$(":selected")|	All selected input elements|
| :checked|	$(":checked")	|All checked input elements|
