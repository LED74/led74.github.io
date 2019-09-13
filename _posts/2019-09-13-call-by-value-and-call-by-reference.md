---
layout: post
title: "call by value and call by reference"
subtitle: "call by value and call by reference"
categories: Programming
tags: Javascript
---

# **Javascript Basic**<br>
if data type in var is primitive data, it's call by value  <br>

*primitive data Type*
- number
- string
- boolean
- null
- undefined

```javascript
var a = 1;
var b = a;
b = 2 ;
console.log(a); // 1 (call by value)
```


if data type in var is Object, it's reference by value  <br>

```javascript
var a = {'id':1};
var b = a;
b.id = 2;
console.log(a.id); // 2 (reference by value)
```

**function and reference**

```javascript
var a = 1;
function func(b){
  b = 2;
  // call by value
}
func(a);
console.log(a); // 1
```

```javascript
var a = {'id':1};
function func(b){
  b = {'id:2'};
  // b just created a new object so it's not affected to a's value
}
func(a);
console.log(a); // 1
```


```javascript
var a = {'id':1};
function func(b){
  b.id = 2;
  // call by reference
}
func(a);
console.log(a); // 2
```
