---
layout: post
title: "closure, arguments, apply"
subtitle: "closure, arguments, apply"
categories: Programming
tags: Javascript
---
# **Javascript Basic**

**Closure**
>A closure is the combination of a function and the lexical environment within which that function was declared.

```javascript
//example
function outter(){
  var title = 'coding everybody';
  function inner(){
    alert(title);
  }
  inner();
}
// result : coding everybody
// as you can see, inner function can access to the var title 
// even though title is located outside of the function. That's a Closure
```

Private variable
```javascript
function factory_movie(title){
  return {
    get_title : function (){
      return title;
    }
    set_title : function(_title){
        if(typeof _title === 'string'){
            title = _title;
        }else{
            alert('subject should be string type');
        }
    }
  }
}
ghost = factory_movie('Ghost in the shell');
matrix = factory_movie('Matrix');

alert(ghost.get_title); // Ghost in the shell
alert(matrix.get_title); // Matrix
```

**Parameter and Arguments**
```javascript
function sum(){
  var i, _sum = 0;
  for(i=0; i<arguments.length; i++){ 
    // even though there is no parameter but js can access to arguments
    document.write(i+' : '+arguments[i]+'<br />');
    _sum += arguments[i];
  }
  return _sum;
}
document.write('result : ' + sum(1,2,3,4));
```

**Apply**
>The apply() method calls a function with a given this value, and arguments provided as an array (or an array-like object).

```javascript
o1 = {val:1, val2:2, val3:3}
o2 = {v1:10, v2:50, v3:100, v4:25}
function sum(){
  var _sum = 0;
  for(name in this){
    _sum += this[name];
  }
  return _sum;
}
alert(sum.apply(o1)) // 6
alert(sum.apply(o2)) // 185
```