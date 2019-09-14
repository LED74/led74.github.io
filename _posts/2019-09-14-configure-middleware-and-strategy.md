---
layout: post
title: "configure middleware and strategy"
subtitle: "configure middleware and strategy"
categories: Programming
tags: NodeJS
---

# **NodeJS** <br>

FYI) You can also find reference here <br>
[https://github.com/expressjs/session](https://github.com/expressjs/session)

add code. <br>

app.js
```javascript
app.use(session({
	secret: 'keyboard cat', // this is a key value to encrypt the session data
  resave: false,
  saveUninitialized: true,
}))


app.use(passport.initialize())
app.use(passport.session())
app.use(flash()) // flash helps send a message easily.
```

index.js in Folder join
```javascript
var passport = require('passport')
var LocalStrategy = require('passport-local').Strategy


router.get ('/', function(req,res){ //router re configure
  //console.log('get url')
  var msg
  var errMsg = req.flash('error')
  if(errMsg) msg = errMsg;
  res.render('join.ejs', {'message' : msg})
  //res.sendFile(path.join(__dirname, '../../public/join.html'))
})


//passport.serialize
passport.serializeUser(function(user,done){
	console.log('passport session save : ',user.id)
	done(null, user.id)
});
passport.deserializeUser(function(id,done){
	console.log('passport session get id  : ',id)
	done(null, id);
})


passport.use('local-join', new LocalStrategy({
    usernameField: 'email', //email means input value(email) in join.ejs file
    passwordField: 'password', //password means input value(password) in join.ejs file
    passReqToCallback : true
  }, function(req, email, password, done) { 
      //console.log('local-join callback called');
      var query = connection.query('select * from user where email=?', [email], function(err,rows){
        if(err) return done(err); // Error handling

        if(rows.length){ // if value already exist in Database
          return done(null, false, {message : 'your email is already used'})
          // return the message using flash
        }else{ //if there is no same value 
					var sql = {email: email, pw:password, name:'euido'};
					var query = connection.query('insert into user set ?', sql, function(err,rows){
						if(err) throw err
						return done(null, {'email' : email, 'id' : rows.insertId})
					})
        }

      })
  }
));


router.post('/', // authenticate handling using local-join
  passport.authenticate('local-join', {
     successRedirect: '/main', // when success
     failureRedirect: '/join', // when failure
     failureFlash: true })
);

```

join.ejs in Folder views
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
    <section class="messages"> <%= message %> </section>
    <!-- add message in view part. -->
    <form action="/join" method="post">
    email : <input type="text" name="email"></br>
    password : <input type="text" name="password"><br>
    <input type="submit">
    </form>
  </body>
</html>

```

main.js in Folder main
```javascript
var express = require('express')
var app = express()
var router = express.Router();
var path = require('path')

router.get('/', function(req,res){
  console.log('main.js is loaded')
  res.sendFile(path.join(__dirname, '../../public/main.html'))
});

// be able to export router from other file
module.exports = router;
```