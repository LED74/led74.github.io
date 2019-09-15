---
layout: post
title: "configure login logic"
subtitle: "configure login logic"
categories: Programming
tags: NodeJS
---

# **NodeJS** <br>

1. configure routing <br>

add router settings in index.js in folder router
```javascript
var login = require('./login/index')

router.use('/login',login)
```

index.js in folder login
```javascript
router.get ('/', function(req,res){
  var msg
  var errMsg = req.flash('error')
  if(errMsg) msg = errMsg;
  res.render('login.ejs', {'message' : msg})
})

//passport.serialize
passport.serializeUser(function(user,done){
	console.log('passport session save : ',user.email)
	done(null, user.email)
});

passport.deserializeUser(function(id,done){
	console.log('passport session get id  : ',id)
	done(null, id);
})

passport.use('local-login', new LocalStrategy({
    usernameField: 'email',
    passwordField: 'password',
    passReqToCallback: true
  }, function(req, email, password, done) {
      var query = connection.query('select * from user where email=?', [email], function(err,rows){
        if(err) return done(err); // when sql error

        if(rows.length){ // if any value
          return done(null, {'email' : email, 'id' : rows[0].UID}) // return email, id
        }else{
					return done(null, false, {'message' : 'your login info is not found'})
        } // when login info already in DB, return the message. -> value go to info
    })
  }
));

// we use ajax so need to response as json type (using custom callback)
router.post('/', function(req, res, next) {
	passport.authenticate('local-login', function(err, user, info) {
		if(err) res.status(500).json(err); // when error
		if(!user) return res.status(401).json(info.message); // when user doesn't exist

		req.logIn(user, function(err){
			if(err) { return next(err); }
			return res.json(user);
		})
	})(req,res,next); // resonse return value
});
```

email.ejs in Folder views
```javascript
<!DOCTYPE html>
<html>
  <head>
    <meta charset="uft-8">
    <title>email form</title>
  </head>
  <body>
    <form action="/email/form" method="post">
      email : <input type="text" name="email"><br/>
      passwd : <input type="password" name="password"><br/>
    </form>
    <button class="ajaxsend">login</button>

    <div class="result"></div>

    <script>
      document.querySelector('.ajaxsend').addEventListener('click',function(){
        var email = document.getElementsByName('email')[0].value;
        var password = document.getElementsByName('password')[0].value;
        sendAjax('http://localhost:3000/login',{'email' : email,
         'password' : password});

      })

      function sendAjax(url, data){
        data = JSON.stringify(data);

        var xhr = new XMLHttpRequest();
        xhr.open('POST', url);
        xhr.setRequestHeader('Content-Type', "application/json");
        xhr.send(data);

        xhr.addEventListener('load', function(){
          var result = JSON.parse(xhr.responseText);
          var resultDiv = document.querySelector(".result");
          // if we received the data (result.email)
          if(result.email) resultDiv.innerHTML = "welcome, "+result.email + "!!"
          // if there is no data, show the result message.
          else resultDiv.innerHTML = result;
          console.log(xhr.responseText);
        });
      }
    </script>
  </body>
</html>

```
