---
layout: post
title: "Standard Built-in Object and Expansion"
subtitle: "Standard Built-in Object and Expansion"
categories: Programming
tags: Javascript
---

# **Javascript Basic**<br>
**Standard Built-in Object**
- Object
- Function
- Array
- String
- Boolean
- Number
- Math
- Date
- RegExp


**Standard Built-in Object Expansion using prototype<br>**

for example, we want to make a function which pick one randomly from an array.

normally we can make function like..
```javascript
var arr = new Array('seoul', 'new york', 'ladarkh', 'pusan', 'Tsukuba')
function getRandomValueFromArray(arr){
    var index = Math.floar(arr.length * Math.random());
    return arr[index];
}
console.log(getRandomValueFromArray);
```

but now we want to make the function and use again later.
```javascript
Array.prototype.rand = function(){
    var index = Math.floor(this.length*Math.random());
    return this[index];
}
var arr = new Array('seoul','new york','ladarkh','pusan', 'Tsukuba');
console.log(arr.rand());
```

Think about the diffrence between two examples deeply. 