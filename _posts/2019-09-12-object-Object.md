---
layout: post
title: "object Object"
subtitle: "object Object"
categories: Programming
tags: Javascript
---

# **Javascript Basic**<br>
object Object is Object which have no inheritance. <br>

How to use Object API<br>
Object Reference <br>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

What is the usage diffrence between two methods?

```javascript
//Object.keys()
var arr = ["a", "b", "c"];
console.log('Object.keys(arr)', Object.keys(arr)); // return key values.
```

```javascript
//Object.prototype.toString()
var o = new Object();
console.log('o.toString()', o.toString());
```
in case of second methods, only Object can use the method.

**Object extension** <br>
```javascript
Object.prototype.contain = function(neddle) {
    for(var name in this){
        if(this[name] === neddle){
            return true;
        }
    }
    return false;
}
var o = {'name':'euido', 'city':'seoul'}
console.log(o.contain('euido')); //true
var a = ['euido','leezche','grapittie'];
console.log(a.contain('leezche')); //true
```

**be careful when you extend Object** <br>
```javascript
Object.prototype.contain = function(neddle) {
    for(var name in this){
        if(this[name] === neddle){
            return true;
        }
    }
    return false;
}
var o = {'name':'euido', 'city':'seoul'}
var a = ['euido','leezche','grapittie'];

for(var name in o){
  if(o.hasOwnPropery(name)){
    console.log(name);
  }
}
// the reason why we need to use hasOwnPropery function is
// if o has also contain methods so it shows for loop as well.
```