---
layout: post
title: "template literal"
subtitle: "template literal"
categories: Programming
tags: Javascript
---
# **Javascript ES6,ES7,ES8** <br>

**template literal**<br>

you can use template literal like this..
```javascript
const sayHi = (aName = "anon") => `hello ${aName} lovely to have you`;

console.log(sayHi());
```

**HTML Fragments using template literal**<br>

Example 1.<br> 
index.html
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head></head>
  <body>
    <div class="wrapper"></div>
  </body>
</html>
```

you write the code before..
```javascript
const wrapper = document.querySelector(".wrapper");

const addWelcome = () => {
  const div = document.createElement("div");
  const h1 = document.createElement("h1");
  h1.innerText = "Hello";
  div.append(h1);
  wrapper.append = div;
}

setTimeout(addWelcome, 5000);
```

if we use the template literal, template literal consider your indent as well.
```javascript
const wrapper = document.querySelector(".wrapper");

const addWelcome = () => {
  const div = `
    <div class="hello">
      <h1 class="title">Hello<h1>
    </div>
  `;
  wrapper.append = div;
}

setTimeout(addWelcome, 5000);
```

Example 2.
```javascript
const wrapper = document.querySelector(".wrapper");

const friends = ["me", "Euido", "Josh", "Mark"];

const ul = document.createElement("ul");
friends.forEach(friend => ul.append(`<li>${friend}</li>`))

wrapper.append(ul);
```

you can simply change the code using template literal
```javascript
const wrapper = document.querySelector(".wrapper");

const friends = ["me", "Euido", "Josh", "Mark"];

const list = `
    <h1>People i love<h1>
    <ul>
      ${friends.map(friend => `<li>${friend}</li>`).join(" ")}
    </ul>
`;

wrapper.append(ul);
```

**Various String functions** <br>

1.include <br>
```javascript
const isEmail = (email) => email.includes("@");

console.log(isEmail("leeeuido@gmail.com"));
```

2.repeat<br>
```javascript
const CC_NUMBER = "6060";

const displayName = `${"*".repeat(10)}${CC_NUMBER}`;

console.log(displayName);
```

3.startWith, endsWith
```javascript
const name = "Mr. LEE";

console.log(name.startWith("Mr."));

console.log(name.endsWith("LEE"));

```