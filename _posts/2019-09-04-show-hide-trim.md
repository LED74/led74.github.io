---
layout: post
title: "show, hide, trim"
subtitle: "show, hide, trim"
categories: Programming
tags: jQuery
---

# **jQuery** <br>

Show / Hide

```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Insert title here</title>
<script type="text/javascript" src="/jquery/jquery-1.12.4.min.js"></script>
<script type="text/javascript">
	$(function(){
		$("#showButton").click(function(){
			//display:block;
			//$("#showhide").show();
			//$("#showhide").fadeIn();
			$("#showhide").slideDown({
				duration : 100
			});
		});
		$("#hideButton").click(function(){
			//display:none;
			//$("#showhide").hide();
			//$("#showhide").fadeOut();
			$("#showhide").slideUp();
		});
	})
</script>
</head>

<body>
<input type="button" id="showButton" value="show" />
<input type="button" id="hideButton" value="hide" />
<div id="showhide" style="border : 1px solid red; display: none;">
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
	Hello, this is jQuery <br/>
</div>

</body>

</html>
```


```javascript
<html>
<head>
  <script type="text/javascript" src="/jquery-1.12.4.min.js"></script>
  <script type="text/javascript">
    $(function(){
      //click load button
      $("#loadButton").click(function(){
        $.ajax({
          url : "/dummy.json",
          type : 'GET',
          dataType : "json",
          success : function(data){
            $("#titleLayer").html("<h2>"+data.title+"</h2>");
            $(".titleLayer").html("<h1>"+data.subject+"</h1>");

            var list = data.list;
            var tableTag = "";
/*
            for(var i = 0; i<list.length; i++){
              tableTag += "<tr><td>" + list[i].subject+"</td><td>" + list[i].content + "</td></tr>";
            }
            $("table").html(tableTag);
*/
            $.each(list,function(index,data){
              tableTag += "<tr><td>" + data.subject+"</td><td>" + data.content + "</td></tr>";
            })
            $("table").html(tableTag);
          }
        });
      })
    });
  </script>
</head>
<body>
    <input type="button" value="load" id=loadButton"/>
    <div id="titleLayer"></div>
    <div class="subjectLayer"></div>
    <table width="100%" border="1"></table>
</body>
</html>
```

Trim

```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Insert title here</title>
<script type="text/javascript" src="/jquery/jquery-1.12.4.min.js"></script>
<script type="text/javascript">
	$(function(){
		$("#trimButton").click(function(){
				$("#trimText").val($("#trimText").val().trim());
		})
	});

</script>
</head>

<body>
	<input type="text" id="trimText" value="        B l a n k            " />
	<input type="button" id="trimButton" value="trim" />
</body>

</html>
```