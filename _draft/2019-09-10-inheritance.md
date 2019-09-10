---
layout: post
title: "global object and this"
subtitle: "global object and this"
categories: Programming
tags: Javascript
---
# **Javascript Basic**

Global object is special object. all object is property of the Global object

```javascript
function func(){
  alert('Hello?');
}
func();
window.func();
``` 

Window api <br>
[https://developer.mozilla.org/en-US/docs/Web/API/Window](https://developer.mozilla.org/en-US/docs/Web/API/Window) <br>

in Web browser, global object is "Window" <br>
but in node.js, global object is "global" <br>

this means context in function, it can be changeable depending on the situation. <br>

1 . function and this <br>
call function <br>

func is no object so it is belong to Window object so this is Window.
```javascript
function func(){
  if(window === this){ // Window === this
    document.write("window === this");
  }
}
func();
```

2 . method and this <br>

func is belong to object o, o belong to object Window. so this is object o. <br>
```javascript
var o = {
  func : function() {
    if(o === this){ // o === this
      document.write("o === this");
    }
  }
}
```

3 . constructor and this<br>

```javascript
var funcThis = null;

function Func(){
  funcThis = this;
}
// funcThis === null
var o1 = Func();  // call function
// funcThis === object Window
if(funcThis === window) {
  document.write('window </br>');
}
var o2 = new Func(); // call constructor
// funcThis === Object o2
if(funcThis === o2) {
  document.write('o2 </br>');
}
```

4 . apply and this

```javascript
var o = {}
var p = {}
function func(){
  switch(this){
    case o:
      document.write('b<br />');
      break;
    case p:
      document.write('p<br />');
      break;
    case window:
      document.write('window<br />');
      break;
  }
}
func(); // Window
func.apply(o); // o
func.apply(p); // p
```

