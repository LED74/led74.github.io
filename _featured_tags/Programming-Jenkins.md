---
layout: post
title: "each"
subtitle: "each"
categories: Programming
tags: jQuery
---

# **jQuery** <br>

each loop 

```javascript
<script>
$(function(){
      $("div").each(function(index){
        let txt = $("div").eq(index).find("input[type=text]").val();
        console.log(txt); // first value, second value, third value, fourth Value
      });
      //OR
      $("div").each(function(index){
        let txt = $(this).find("input[type=text]").val();
        // $("div").eq(index) = $(this)
        console.log(txt); // first value, second value, third value, fourth Value
      });    
  });
</script>
<body>
  <div>
    <input type="text" value="first value"/>
  </div>
  <div>
    <input type="text" value="second value"/>
  </div>
  <div>
    <input type="text" value="third value"/>
  </div>
  <div>
    <input type="text" value="fourth value"/>
  </div>
</body>
```


return
```javascript
<script>
$(function(){
      $("div").each(function(index){
          if(index == 1){
            return false;
          }
      });
  });
</script>
<body>
  <div>
    <input type="text" value="first value"/>
  </div>
  <div>
    <input type="text" value="second value"/>
  </div>
  <div>
    <input type="text" value="third value"/>
  </div>
  <div>
    <input type="text" value="fourth value"/>
  </div>
</body>
```
