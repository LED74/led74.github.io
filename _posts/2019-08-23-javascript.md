---
layout: post
title: "Javascript"
subtitle: "Javascript"
categories: Programming
tags: Javascript
---

## **JavaScript Math Object**
[Javascript Math Object](https://www.w3schools.com/js/js_math.asp)

## **String**
Checkpoint

Command Typeof 
```javascript
typeof(1);
typeof("1");
```

<br>
Use "/" letter before use ' as a letter. <br>

There are many functionas related in Javascript String <br>
[https://www.w3schools.com/js/js_string_methods.asp](https://www.w3schools.com/js/js_string_methods.asp)

## **Equals operator**
Difference between == and === <br>
-> The identity (===) operator behaves identically to the equality (==) operator except no type conversion is done, and the types must be the same to be considered equal.
```javascript
alert(null == undefined); //true
alert(null === undefined); //false
// because null and undefined are different type.
alert(true == 1); //true
alert(true === 1); //false
alert(true == '1'); //true
alert(true === '1'); //false

alert(0 === -0); //true
alert(NaN === NaN); //false
```

You can find more information below : 
[https://dorey.github.io/JavaScript-Equality-Table/](https://dorey.github.io/JavaScript-Equality-Table/)

## **Array**
**ADD**<br>
Push() (add one data)
```javaScript
var li = ['a', 'b', 'c', 'd']
li.push('f');
```
Concat() (add multiple data)
```javaScript
var li = ['a', 'b', 'c', 'd']
li.concat('f','g');
```

unshift() (add to the front)
```javaScript
var li = ['a', 'b', 'c', 'd']
li.unshift('z');
```

splice() (select the point that you want to put)
```javaScript
var li = ['a', 'b', 'c', 'd']
li.splice(2, 0, 'b');
```

**DELETE**<br>
Shift() (delete one data from the front)
```javaScript
var li = ['a', 'b', 'c', 'd']
li.unshift();
```

pop() (delete on date from the last)
```javaScript
var li = ['a', 'b', 'c', 'd']
li.pop();
```

**SORT**<br>
```javaScript
sort()
var li = ['d', 'c', 'b', 'a']
li.sort();
```

## **Object**
**Creation**
```javaScript
var grades = {'test':10, 'test2':6, 'test3':8};
// Key:test, test2, test3
// Value:10,6,8
for(key in grades){
  document.write("key : "+key+" value : "+grades[key]+"<br />");
}
```

## **Module**

## **Regular Expression**

```javaScript
var pattern = /a/;
var pattern = new RegExp('a');
// same expression.
```

```javaScript
var pattern = /a/;
pattern.exec('bcdef'); //null
pattern.test('abcde'); //true
pattern.test('bcde'); //false
```

**String.match()**
```javaScript
var pattern = /a/;
var str = 'abcdef';
str.match(pattern); // 
```

**String.replace()**
```javaScript
var pattern = /a/;
var str = 'abcdef';
str.replace(pattern, 'A');
```
Option 
i Option -> (No matter letter is big or small)
g Option -> (print all result)

Regular expression visualizer using railroad diagrams. <br>
https://regexper.com/
```javaScript
(\w+)\s(\w+)
```

**Global var, Local var**
In Javascript, Local var is only valid in function().
it means it's possible below code.
```javaScript
for(var i=0; i<1; i++){
  var name = 'coding everybody';
}
elert(name);
// in case of it, name is global var
``` 

**Closure**
```javaScript
function factory_movie(title){
  return {
    get_title : function (){
      return title;
    }
    set_title : function(_title){
        title = _title
    }
  }
}
ghost = factory_movie('Ghost in the shell');
matrix = factory_movie('Matrix');
```


Reference lecture :
[https://www.inflearn.com/course/html-css-%EA%B0%95%EC%A2%8C-codesquad#](https://www.inflearn.com/course/html-css-%EA%B0%95%EC%A2%8C-codesquad#)


```javaScript
var content = '생활코딩 : http://opentutorials.org/course/1 입니다. 네이버 : http://naver.com 입니다.;
var urlPattern' = \https?\;
var result 
```