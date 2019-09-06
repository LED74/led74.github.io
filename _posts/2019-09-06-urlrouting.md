---
layout: post
title: "URL Routing"
subtitle: "URL Routing"
categories: Programming
tags: NodeJS
---

# **NodeJS** <br>

like this picture, you can routing page with url easily. <br>
app.js<br>
![appjs](https://led74.github.io/assets/img/post/appjs.png)
main.html<br>
![mainhtml](https://led74.github.io/assets/img/post/mainhtml.png)
Internet browser<br>
![browser](https://led74.github.io/assets/img/post/browser.png)

Also, if you use "app.use" function, server set public folder as a static.

```java
var express = require('express')
var app = express()
app.listen(3000, function() {
console.log("start!! express server on port 3000");
});

//function app.use
app.use(express.static('public'))

//url routing
app.get('/', function(req,res){
res.sendFile(__dirname + '/public/main.html')
});


app.get('/main', function(req,res){
res.sendFile(__dirname + '/public/main.html')
});
```