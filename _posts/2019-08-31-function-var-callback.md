---
layout: post
title: "function, var, callback"
subtitle: "function, var, callback"
categories: Programming
tags: Javascript
---
# **Javascript Basic**

**Global var and Local var** <br>
That's important !! need to understand diffrent of three examples.
```javascript
// example 1
let TestValue = "Global";
function ChangeValue(){
	let TestVaule = "Local";
}
document.write(TestValue);
// the answer is : Global

// example 2
let TestValue = "Global";
function ChangeValue(){
	let TestVaule = "Local";
  document.write(TestValue);
}
// the answer is : Local

// example 3
let TestValue = "Global";
function ChangeValue(){
	TestVaule = "Local";
}
document.write(TestValue);
// the answer is : Global
``` 

**Function as a value** <br>
Function is object in javascript.
that means function can be value in javascript.
```javascript 
function a(){} // it means var a  = function(){}
  
a = {
  b:function(){ // b is methods of object a
  }
}
// object a has key b and value function
```

```javascript
function cal(func num){
  return func(num)
}
function increase(num){
  return num+1
}
function decrease(num){
  return num-1
}
alert(cal(increase,1));
alert(cal(decrease,1));
```

**Callback**
```javascript
function sortNumber(a,b){
  return b-a;
}
var numbers = [20,10,9,8,7,6,5,4,3,2,1];
alert(numbers.sort(sortNumber)); // array [20,10,9,8,7,6,5,4,3,2,1]
// sortNumber is callback function.
```