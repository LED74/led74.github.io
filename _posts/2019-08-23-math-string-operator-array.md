---
layout: post
title: "math, string, operator, array"
subtitle: "math, string, operator, array"
categories: Programming
tags: Javascript
---
# **Javascript Basic**

## **Javascript Math Object**
The JavaScript Math object allows you to perform mathematical tasks on numbers. <br>
If we know the existence of these kinds of function, we can save time.<br>
```javascript
// Example
Math.PI       // returns PI
Math.round()  // returns the value of x rounded to its nearest integer:
Math.max(0, 150, 30, 20, -8, -200);  // returns 150
Math.min(0, 150, 30, 20, -8, -200);  // returns -200
```
You can find information in detail below.  <br>
[Javascript Math Object](https://www.w3schools.com/js/js_math.asp)

## **String**

Expressions - typeof
```javascript
console.log(typeof 42); // expected output: "number"
console.log(typeof 'blubber'); // expected output: "string" 
console.log(typeof true); // expected output: "boolean"
console.log(typeof declaredButUndefinedVariable); // expected output: "undefined";
```
You can find information in detail below.  <br>
[Reference typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof)

Expressions - String Methods <br>
```javascript
// String Length
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
// Result : 26

// Finding a String in a String
var str = "Please locate where 'locate' occurs!";
var pos = str.indexOf("locate");
// Result : 7

// Slice() Method
var str = "Apple, Banana, Kiwi";
var res = str.slice(7, 13);
// Result : Banana
```
You can find information in detail below.  <br>
[JavaScript String Methods](https://www.w3schools.com/js/js_string_methods.asp)


## **Equals operator**
Difference between "==" and "===" <br>
> The identity (===) operator behaves identically to the equality (==) operator except no type conversion is done, <br>
and the types must be the same to be considered equal. 


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

You can find information in detail below. <br>
[Javascript equality table](https://dorey.github.io/JavaScript-Equality-Table/)

## **Array**
**ADD**<br>
Push() (add one data)
```javascript
var li = ['a', 'b', 'c', 'd'];
li.push('f');
```
Concat() (add multiple data)
```javascript
var li = ['a', 'b', 'c', 'd'];
li.concat('f','g');
```

unshift() (add to the front)
```javascript
var li = ['a', 'b', 'c', 'd'];
li.unshift('z');
```

splice() (select the point that you want to put)
```javascript
var li = ['a', 'b', 'c', 'd'];
li.splice(2, 0, 'b');
```

**DELETE**<br>
Shift() (delete one data from the front)
```javascript
var li = ['a', 'b', 'c', 'd'];
li.unshift();
```

pop() (delete on date from the last)
```javascript
var li = ['a', 'b', 'c', 'd'];
li.pop();
```

**SORT**<br>
```javascript
sort()
var li = ['d', 'c', 'b', 'a'];
li.sort();
```