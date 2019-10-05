---
layout: post
title: "Hoisting and TDZ(Temporal Dead Zone)"
subtitle: "Hoisting and TDZ(Temporal Dead Zone)"
categories: Programming
tags: Javascript
---
# **Javascript ES6,ES7,ES8**

There are two different codes. <br>

1.
```javascript
var myName = "nico";
console.log(myName);
// result = nico
```

2.
```javascript
console.log(myName);
var myName = "nico";
// result = undefined
```

first sentence makes sense. <br>
In case of number 2, we expect that we will have an error. <br>
but the result is undefined. why? <br>

because all Variable become "Hoisting". so what is "Hoisting"? <br>
Below code is same as number 2.
```javascript
var myName;
console.log(myName);
myName = "nico";
// result = undefined
```
Hoisting helps to move Variable declaration to top of the code. <br>

That's why we would better to use let or const instead of var. <br>

if we use 'let' instead of 'var' code will be like.. <br>
and we can find the error result. why? <br>
```javascript
console.log(myName);
let myName = "nico";
// result = uncaught reference error: myName is not defined
```
let also have hoisting but let has TDZ(Temporal Dead Zone)<br>
and nobody can access before myName bind with a value

```javascript
let myName;
console.log(myName);
myName = "nico"; //after this line, we can access myName
// result = uncaught reference error: myName is not defined
```
code after hoisting will be the same as var's case. <br>

