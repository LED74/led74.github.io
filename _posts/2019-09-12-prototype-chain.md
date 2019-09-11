---
layout: post
title: "prototype chain"
subtitle: "prototype chain"
categories: Programming
tags: Javascript
---

# **Javascript Basic**<br>
prototype
```javascript
function Ultra(){}
Ultra.prototype.ultraProp = true;

function Super(){}
Super.prototype = new Ultra();

function Sub(){}
Sub.prototype = new Super();

var o = new Sub();
console.log(o.ultraProp);
// Result : true
// because Sub has ultraProp? no ->
// Super has ultraProp? no ->
// Ultra has ultraProp? Yes ->
// value? -> true
```

```javascript
function Ultra(){}
Ultra.prototype.ultraProp = true;

function Super(){}
Super.prototype = new Ultra();

function Sub(){}
Sub.prototype = new Super();
Sub.prototype.ultraProp = 2;

var o = new Sub();
console.log(o.ultraProp);
// Result : 2
// Sub has ultraProp? Yes ->
// Value? -> 2
```

another example
```javascript
function Ultra(){}
Ultra.prototype.ultraProp = true;

function Super(){}
Super.prototype = new Ultra();

function Sub(){}
var s = new Super();
s.ultraProp = 3;
Sub.prototype = s;
//it means Sub.prototype.ultraProp = 3;
// Sub.prototype = new Super();
// if we remove s, we can understand it's same with above codes.

var o = new Sub();
console.log(o.ultraProp);
```
