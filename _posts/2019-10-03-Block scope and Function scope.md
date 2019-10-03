---
layout: post
title: "Block scope and Function scope"
subtitle: "Block scope and Function scope"
categories: Programming
tags: Javascript
---
# **Javascript ES6,ES7,ES8**

Var -> Function scope <br>
Let, Const -> Block scope <br>

1.Var has Function scope and console.log can access hello.

```javascript
if(true){
  var hello = 'hi';
}
console.log(hello);
// result : hi
```


2.let has Block scope and console.log cannot access hello. <br>
because let hello is nested by {} (Block).
```javascript
if(true){
  let hello = 'hi';
}
console.log(hello);
// result : error
```

3.Var has Function scope and console.log cannot access hello. <br>
because Var hello is nested by function.
```javascript
function(){
  var hello = 'hi';
}
console.log(hello);
// result : error
```
