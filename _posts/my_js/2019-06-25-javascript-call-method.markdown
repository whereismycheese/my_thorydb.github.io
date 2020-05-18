---
layout: post
title:  "call()"
subtitle:   "this is subtitle for call()"
categories: javascript
tags: javascript web-dev
comments: true
header-img: img/javascript/js_call.jpg
---
```javascript
그신발.call(나);
그신발.call(당신);
```

## 개요
> Javascript Function Call()  

- 목차
	- [HOW I SEE](#how-i-see)
	- [문제 상황 1](#문제-상황-1)
	- [문제 상황 1 해결](#문제-상황-1-해결)
	- [추가 특징](#추가-특징)


## HOW I SEE
---
:point_right: B오브젝트가 A오브젝트의 함수(메서드)를 사용하는 방법?  
`A오브젝트.A오브젝트에속한_메서드.call(B오브젝트)`  


## 문제 상황 1
---
```javascript
var person = {
  firstName:"John",
  lastName: "Doe",
  fullName: function () {
    return this.firstName + " " + this.lastName;
  }
}
person.fullName();   // Will return "John Doe"
```
person의 fullName()을 다른 오브젝트가 사용하고 싶다면?

## 문제 상황 1 해결
---
person의 fullName()을 사용하기 위한 특징을 가진 오브젝트를 따로 만들고
call()을 이용하면 된다
```javascript
var person = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
var person1 = {
  firstName:"John",
  lastName: "Doe"
}
var person2 = {
  firstName:"Mary",
  lastName: "Doe"
}
person.fullName.call(person2);  // Will return "Mary Doe"
```


## 추가 특징
---
call()은 다른 arguments들도 받아들일 수도 있다.
```javascript
var person = {
  fullName: function(city, country) {
    return this.firstName + " " + this.lastName + "," + city + "," + country;
  }
}
var person1 = {
  firstName:"John",
  lastName: "Doe"
}
person.fullName.call(person1, "Oslo", "Norway");
```
