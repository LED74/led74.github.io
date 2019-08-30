---
layout: post
title: "Javascript"
subtitle: "Javascript"
categories: Programming
tags: Javascript
---

## **JavaScript Math Object**
[Javascript Math Object](https://www.w3schools.com/js/js_math.asp)

## **String**
Checkpoint

Command Typeof 
```javascript
typeof(1);
typeof("1");
```

<br>
Use "/" letter before use ' as a letter. <br>

There are many functionas related in Javascript String <br>
[https://www.w3schools.com/js/js_string_methods.asp](https://www.w3schools.com/js/js_string_methods.asp)

## **Equals operator**
Difference between == and === <br>
-> The identity (===) operator behaves identically to the equality (==) operator except no type conversion is done, and the types must be the same to be considered equal.
```javascript
alert(null == undefined); //true
alert(null === undefined); //false
// because null and undefined are different type.
alert(true == 1); //true
alert(true === 1); //false
alert(true == '1'); //true
alert(true === '1'); //false

alert(0 === -0); //true
alert(NaN === NaN); //false
```