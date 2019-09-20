---
layout: post
title: "RESTful API-GET/POST"
subtitle: "RESTful API GET/POST"
categories: Programming
tags: NodeJS
---

# **NodeJS** <br>

email.ejs
```javascript
<script>
    document.querySelector('.showWrap').addEventListener('click', function(e) {
        let url, method, data, fn;
        const target = e.target;
        const li = target.closest('LI');
        const showResult = li.querySelector(".showResult");
        const type = li.className;

        if(target.tagName !== "BUTTON") return;

        switch (type) {
            case "get_all":
                url = "/movie";
                method = "GET";
                fn = function(result) {
                    if(result.result === '1') {
                        let titles = result.data.reduce(function(pre,next){
                            pre += "<li>" + next.title + "</li>"
                            return pre;
                        },"");
                        showResult.innerHTML = "<ul>" + titles + "</ul>";
                    } else {
                     showResult.innerHTML = "list not found";
                    }
                }
                break;
            case "post":
                url = "/movie";
                method = "POST";
                let inputs = [].slice.call(document.querySelector("form").elements);
                console.log(inputs);
                data = inputs.reduce(function(pre,next) {
                    pre[next.name] = next.value;
                    return pre;
                }, {});
                console.log(data);
                fn = function (result) {
                    if(result.result === 1) showResult.innerHTML = "새로운 영화 데이터가 잘 추가됐습니다.";
                    else showResult.innerHTML = "list not found";
                }
                break;
            case "get_id":
                url = "/movie/"+li.getElementsByTagName("input")[0].value;
                method = "GET";
                fn = function(result) {
                    if(result.result === 1) {
                        showResult.innerHTML = result.data[0].actor;
                    }else {
                        showResult.innerHTML = "해당하는 영화가 없네요..";
                    }
                }
                break;
            case "delete_id":
                url = "/movie/"+li.getElementsByTagName("input")[0].value;
                method = "DELETE";
                fn = function(result) {
                    if(result.result === 1) {
                        showResult.innerHTML = "선택한영화" + result.data+ "가 잘 삭제됐습니다";
                    }else{
                        showResult.innerText = "해당영화가 없습니다";
                    }
                }
                break;
            default:
                // statements_def
                console.log("default");
                break;
        }
        sendAjax(url, method, data, fn);
    })
```

index.js in folder movie
```javascript
// 1. /movie , GET
router.get('/', function(req,res){
    var responseData = {};

  	var query = connection.query('select title from movie', function(err,rows){
  		if(err) throw err;
  		if(rows.length) {
  	  	responseData.result = "1";
  			responseData.data = rows;
  		} else {
  			responseData.result = "0";
  			responseData.data = "";
  		}
  		res.json(responseData)
  })
})

// 2. /movie , POST
router.post('/', function(req,res){
    var title = req.body.title;
    var type = req.body.type;
    var grade = req.body.title;
    var actor = req.body.actor;

    var sql = {title, type, grade, actor};
    console.log(sql)
    var query = connection.query('insert into movie set ?', sql, function(err,rows){
      if(err) throw err
      console.log(res)
      return res.json({'result' : 1});
    })
})

```
