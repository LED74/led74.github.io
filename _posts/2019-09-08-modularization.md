---
layout: post
title: "modularization"
subtitle: "modularization"
categories: Programming
tags: NodeJS
---

# **NodeJS** <br>

if project size is getting bigger, we need to do modularization (MVC). <br>

so, I created index.js file newly <br>
index.js
```javascript
// import file for basic
var express = require('express')
var app = express()
var router = express.Router();
var path = require('path')

// move the routers from app.js to index.js because all router will be stored in this file.
var main = require('./main')
var email = require('./email')

//url routing
router.get('/', function(req,res){
res.sendFile(path.join(__dirname, '../public/main.html')) });

router.use('/main',main)
router.use('/email',email)

module.exports = router;
```

app.js
```javascript
var express = require('express')
var app = express()
var bodyParser = require('body-parser')
var router = require('./router/index')

app.listen(3000, function() {
console.log("start!! express server on port 3000"); });

// removed all lines related to router function 
app.use(express.static('public'))
app.use(bodyParser.json())
app.use(bodyParser.urlencoded({extended:true}))
app.set('view engine', 'ejs')

// only use index.js as a main router here.
// all detail router will be mentioned in index.js
app.use(router)
```