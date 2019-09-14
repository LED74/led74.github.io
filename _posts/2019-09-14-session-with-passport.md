---
layout: post
title: "session with passport"
subtitle: "session with passport"
categories: Programming
tags: NodeJS
---

# **NodeJS** <br>

we did last time for session <br>
app.js
```javascript
// passport.serialize
passport.serializeUser(function(user,done){
	console.log('passport session save : ',user.id)
	done(null, user.id)
});
passport.deserializeUser(function(id,done){
	console.log('passport session get id  : ',id)
	done(null, id);
})
```

main.js in Folder main
```javascript
var express = require('express')
var app = express()
var router = express.Router();
var path = require('path')

router.get('/', function(req,res){
  console.log('main.js is loaded', req.user)
  // we can access with req.user because of the serialize from app.js
  var id = req.user;
  res.render('main.ejs', {'id' : id})
  // and we use render(main.ejs) instead of sendFile.
});

// be able to export router from other file
module.exports = router;
```


main.ejs
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="uft-8">
    <meta name="description" content="">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>email ejs template</title>
  </head>
  <body>
    <h1>main page</h1>

    <h3>welcome, we have  <%=id %> members in total! </h3>

    <p>nice to meet you</p>
    <script src="main.js"></script>
  </body>
</html>
```

