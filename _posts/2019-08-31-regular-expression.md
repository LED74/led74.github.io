---
layout: post
title: "regular expression"
subtitle: "regular expression"
categories: Programming
tags: javascript
---

# **Javascript Basic**

## **Module**
## **Regular Expression**

two ways to make regular expression in JS.
```javascript
var pattern = /a/;
// If the regular expression remains constant, using this can improve performance. 

var pattern = new RegExp('a');
// same expression.
```

```javascript
var pattern = /a/;
pattern.exec('bcdef'); //null
pattern.test('abcde'); //true
pattern.test('bcde'); //false
```

**String.match()**
```javascript
var pattern = /a/;
var str = 'abcdef';
str.match(pattern); // 
```

**String.replace()**
```javascript
var pattern = /a/;
var str = 'abcdef';
str.replace(pattern, 'A');
```
Option <br>
Option i -> (No matter letter is big or small) <br>
Option g -> (print all result)

Regular expression visualizer using railroad diagrams. <br>
[reg exp simulator online](https://regexper.com/) <br>
```javascript
(\w+)\s(\w+)
```
You can find information in detail below.  <br>
[regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)