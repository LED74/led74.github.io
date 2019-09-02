---
layout: post
title: "css control"
subtitle: "css control"
categories: Programming
tags: jQuery
---

# **jQuery** <br>

CSS Control

```javascript
<script>
$(function(){
    //css()
    $("div:eq(0)").css("color", "red");
    $("div:eq(0)").css("font-weight","bold");
  });
</script>
<body>
  <div>control style1</div>
  <div>control style2</div>
</body>
```

```javascript
<head>
<style type="text/css">
  .sample1{
    color : red;
    font-weight : bold;
  }
  .sample2{
    color : green;
  }
</style>

</head>
<script>
$(function(){
    //addClass("ClassName") add className to selected selector
    $("#sampleDiv1").addClass("sample2");
    //removeClass("ClassName") delete className from selected selector
    $("#sampleDiv1").removeClass("sample2");
    //hasclass("ClassName") check whether selected selector has className (true/false)
    let flag = $("#sampleDiv1").hasClass("sample2");
    console.log(flag);
  });
</script>
<body>
  <div id="sampleDiv">control style1</div>
  <div id="sampleDiv2">control style2</div>
</body>
```


