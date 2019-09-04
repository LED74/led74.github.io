---
layout: post
title: "empty, remove, index"
subtitle: "empty, remove, index"
categories: Programming
tags: jQuery
---

# **jQuery** <br>

Empty
```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Insert title here</title>
<script type="text/javascript" src="/jquery/jquery-1.12.4.min.js"></script>
<script type="text/javascript">
	$(function(){
		$("#button").click(function(){
			// only remove contents -> empty();
			$("#showhide").empty();
			// remove layer -> remove();
			$("#showhide").remove();
		})
	});

</script>
</head>

<body>
	<input type="button" id="button" value="hide" />
	<div id="showhide" style="border : 1px solid red;">
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

Example using Remove function
```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Insert title here</title>
<script type="text/javascript" src="/jquery/jquery-1.12.4.min.js"></script>
<script type="text/javascript">
	$(function(){
		$(".btn").click(function(){
			$(this).parent().remove();
		})
	});

</script>
</head>

<body>
	<div id="showhide" style="border : 1px solid red;">
		Hello, this is jQuery <br/>
		<input type="button" class="btn" value="delete" />
	</div>
	<div id="showhide" style="border : 1px solid red;">
		Hello, this is jQuery2 <br/>
		<input type="button" class="btn" value="delete" />
	</div>
</body>

</html>
```

Index
```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Insert title here</title>
<script type="text/javascript" src="/jquery/jquery-1.12.4.min.js"></script>
<script type="text/javascript">
	$(function(){
		$(".btn").click(function(){
			$(".layer").hide();
			$(".layer").eq($(".btn").index(this)).slideDown();
		})		
	});

</script>
</head>

<body>
	<input type="button" class="btn" value="button1" />
	<input type="button" class="btn" value="button2" />
	<input type="button" class="btn" value="button3" />

	<div class="layer" style="display: none">
		Layer1<br/>
		Layer1<br/>
		Layer1<br/>
	</div>
	<div class="layer" style="display: none">
		Layer2<br/>
		Layer2<br/>
		Layer2<br/>
	</div>
	<div class="layer" style="display: none">
		Layer3<br/>
		Layer3<br/>
		Layer3<br/>
	</div>
</body>

</html>
```