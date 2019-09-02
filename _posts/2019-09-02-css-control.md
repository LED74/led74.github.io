---
layout: post
title: "selector"
subtitle: "selector"
categories: Programming
tags: jQuery
---

# **jQuery** <br>

Selector

```javascript
<script>
$(function(){
    $("#xxx").val(); //  id
    $(".xxx").val(); //  class
    $("input[class=text]") // class = text1
    $("input[name=textName1]") // name=textName1
  });
</script>
<body>
  <input type="text" name="textName1" class="text1" value="text1" /></br>
  <input type="text" name="textName2" class="text2" value="text2" /></br>
</body>
```

```javascript
<script>
$(function(){
    let checkedRadio = $("input[name=rdo]:checked").val(); // name=textName1
    console.log(checkedRadio); // print second
  });
</script>
<body>
  <input type="radio" name="rdo" checked="checked" value="first" /></br>
  <input type="radio" name="rdo" value="second" /></br> // selected
</body>
```

```javascript
<script>
$(function(){
    //  $("div:eq(0)") = $("div").eq(0) 
    let class2 = $(".class2:eq(1)").html(); // eq means sequence (starts from 0)
    console.log(class2); // print "value2"
  });
</script>
<body>
  <div class="class2">
    <h2>value1</h2>
  </div>
  <div class="class2">
    <h2>value2</h2>
  </div>
</body>
```