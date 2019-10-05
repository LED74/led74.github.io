---
layout: post
title: "Arrow Functions and Default Values"
subtitle: "Arrow Functions and Default Values"
categories: Programming
tags: Javascript
---
# **Javascript ES6,ES7,ES8** <br>
**Arrow function**<br>
This is code without Arrow.
```javascript
const names = ["April", "Paul", "Jack"];

const list_names = names.map(function(item){
                              return "Name : " + item;
                            });
// maps call the function with each item.
// and maps should always have return value.

console.log(list_names);
// Result :  ["Name : April", "Name : Paul", "Name : Jack"]
```

This is code with Arrow function. <br>
```javascript
const names = ["April", "Paul", "Jack"];

const list_names = names.map(item => "Name : " + item);
// second parameter of map function is index also should be nested with ()

console.log(list_names);
// Result :  ["Name : April", "Name : Paul", "Name : Jack"]
```

But... <br>
We cannot use Arrow function all the time. <br>
1.When this include the function.

```javascript
button.addEventListener("Click", function()){
  this.style.backgroundColor = "red";
}
// Result : When user click the button, the backgroundColor of button will be red.
```

```javascript
button.addEventListener("Click", () => this.style.backgroundColor = "red");

// Result : Error
// Because this indicates to Window, not Button object.
```
Conclusion : if you want to use this, you need to use function not Arrow function.

There is another example.
```javascript
const euido = {
  name : "Euido",
  age : 24,
  addYear: () => {
    this.age++;
  }
};
console.log(euido);
euido.addYear();
euido.addYear();
console.log(euido);
// Result : 24
// Because this indicates to Window, not euido Object.
```
it should be like..
```javascript
const euido = {
  name : "Euido",
  age : 24,
  addYear() {
    this.age++;
  }
};
console.log(euido);
euido.addYear();
euido.addYear();
console.log(euido);
```

**Various Arrow functions**<br>

1.find
```javascript
const email = [
  "nco@no.com",
  "naver@google.com",
  "leeeuido@gmail.com",
  "test@test.com"
];

const foundMail = email.find(item => item.includes('@gmail.com'));
console.log(foundMail);
//result : leeeuido@gmail.com
```

2.filter
```javascript
const email = [
  "nco@no.com",
  "naver@google.com",
  "leeeuido@gmail.com",
  "test@test.com"
];

const noGmail = email.filter(item => !item.includes('@gmail.com'));
console.log(noGmail);
//result : [
  "nco@no.com",
  "naver@google.com",
  "test@test.com"
]
```

3.forEach & map
```javascript
emails.forEach(email => {
  console.log(email.split("@")[0]);
});
//result : nco
//         naver
//         test

// We also can express like this..
emails.map(email => console.log(email.split("@")[0]);
//result : nco
//         naver
//         test
```


**Default value**
```javascript
function sayHi(aName = 'Euido'){
  return 'Hello' + aName();
}

console.log(sayHi());
// in this case, if there is no argument, aName has 'Euido' as a Default value
```

we can also express using Arrow function
```javascript
const sayHi = (aName='Euido') => 'Hello'+aName();

console.log(sayHi());
```