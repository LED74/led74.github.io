---
layout: post
title: "Primitive type and wrapper object"
subtitle: "Primitive type and wrapper object"
categories: Programming
tags: Javascript
---

# **Javascript Basic**<br>
primitive data type vs reference data type <br>

*primitive data Type*
- number
- string
- boolean
- null
- undefined

*reference data type
- all except of primitive data type.


*wrapper object*
but.. what is this? str is string (primitive data) <br>
but it behave like object because primitive data has length method
```javascript
var str = 'coding';
console.log(str.length);
console.log(str.charAt(0));
//str(primitive data type) behave like object but it will be removed after the use.
//we call this "wrapper object"
```
