---
layout: post
title: "passport installation"
subtitle: "passport installation"
categories: Programming
tags: NodeJS
---

# **NodeJS** <br>

first, I'm going to change from **res.sendFile** to **res.render**.

before
```javascript
res.sendFile(path.join(__dirname, '../../public/join.html'))
```

after
```javascript
res.render('join.ejs')
```

and made join.ejs file
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="uft-8">
    <meta name="discription" content="">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Join !</title>
    <style>
      .messages{
        color : #963b3b;
        margin-bottom: 16px;
      }
    </style>
  </head>
  <body>
    <h1>Join my website</h1>
    <section class="messages"></section>
    <form action="/join" method="post">
    email : <input type="text" name="email"></br>
    password : <input type="text" name="password"><br>
    <input type="submit">
    </form>
  </body>
</html>
```

Install **Passport** <br>
[http://www.passportjs.org/](http://www.passportjs.org/) <br>
Simple, unobtrusive authentication for Node.js

```shell
sudo npm passport passport-local express-session connect-flash --save-dev
// passport -> authentication module
// passport-local -> handle general login not like facebook login
// express-session -> handle session
// connect-flash -> handling redirect error message
```

add modules in app.js
```javascript
var passport = require('passport')
var LocalStrategy = require('passport-local').Strategy
var session = require('express-session')
var flash = require('connect-flash')
```
