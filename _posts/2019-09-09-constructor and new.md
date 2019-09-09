---
layout: post
title: "constructor and new"
subtitle: "constructor and new"
categories: Programming
tags: Javascript
---
# **Javascript Basic**

Javascript is Prototype-based programming.

**Object declaration** <br>

two ways to create a object <br>

1.
```javascript
var person = {} // Object
person.name = 'euido'; // name : Property
person.introduce = function(){ // introduce : Method
  return 'My name is '+this.name;
}
document.write(person.introduce());
``` 

2.
```javascript
var person = {
  'name' : 'euido',
  'introduce' : function(){
    return 'My name is ' + this.name;
  }
}
document.write(person.introduce());
```
<br>
Constructor <br>

```javascript
function Person(){}
var p = new Person(); // Constructor
p.name = 'euido';
p.introduce = function(){
  return 'My name is '+this.name;
}
```

if we type like this
```javascript
function Person(){}
var p0 = Person(); // p0 = undefined
``` 
but if we use "new",
```javascript
function Person(){}
var p0 = new Person(); // p0 = person{}
``` 
in Javascript, constructor is just function not belong to any
no concept like class in java.

to re-use an object, we can express like..
```javascript
// initialize object
function Person(name){
  this.name = name;
  this.introduce = function() {
    return 'My name is ' + this.name;
  }
}
var p1 = new Person('euido');
document.write(p1.introduce()+"<br />");

var p2 = new Person('leezche');
document.write(p2.introduce());
```


 