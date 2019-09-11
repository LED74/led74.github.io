---
layout: post
title: "inheritance"
subtitle: "inheritance"
categories: Programming
tags: Javascript
---

# **Javascript Basic**<br>

How to make inheritance in JS <br>

```javascript
function Person(name){
  this.name = name;
}
Person.prototype.name = null;
Person.prototype.introduce = function(){
  return 'My name is ' +this.name;
}
function Programmer (name){
  this.name = name;
}
// here, inheritance happened !!!!
Programmer.prototype = new Person();

var p1 = new Programmer('euido');
document.write(p1.introduce()+"<br />");
```

Add new function after inheritance of object.
```javascript
function Person(name){
  this.name = name;
}
Person.prototype.name = null;
Person.prototype.introduce = function{
  return 'My nickname is '+this.name;
}
function Programmer(name){
  this.name = name;
}
Programmer.prototype = new Person();
Programmer.prototype.coding = function(){
  return "hello world";
}
function Designer(name){
  this.name = name;
}
Designer.prototype.design = function(){
  return "design";
}
var p1 = new Programmer('euido');
document.write(p1.introduce()+"<br />");
document.write(p1.coding()+"<br />");

var p2 = new Programmer('test');
document.write(p2.introduce()+"<br />");
document.write(p2.design()+"<br />"); 
```
