---
layout: post
title: "installation"
subtitle: "installation"
categories: Programming
tags: NodeJS
---

# **NodeJS** <br>

before init the npm,
go to NodeJS website and download & install NodeJS


```bash
npm init
```

nodeserver installation. 
discription : nodeserver test
and enter, enter, enter.
```bash
nodeserver
```

web framework download
```bash
npm install express --save
```

as you see express is now added on the dependencies.

![express](https://led74.github.io/assets/img/post/express.png)


test server 
app.js
```javascript
var express = require('express')
var app = express()
app.listen(3000, function()) {
  console.log("start! express server on port 3000");
}
```

Synchronous first, Asynchronous last.


**install nodemon** <br>
nodemon check a source code change and a  pply the change automatically.
```
sudo install nodemon -g 
```
