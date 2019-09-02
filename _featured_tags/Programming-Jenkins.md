---
layout: post
title: "Traversing"
subtitle: "Traversing"
categories: Programming
tags: jQuery
---

# **jQuery** <br>

Traversing

```javascript
<script>
$(function(){
    // parent(), find(), prev(), next()

    // when you want to find child -> find()
    $("table").find("#txt").val(); // value
    $("table").find("tr:eq(0)").find("td:eq(0)").find("#txt").val(); // value
    console.log("txt",txt);

    // when you want to find parent -> parseInt
    $("table").find("#txt").parent().val(); // <td>

    // when you want to find next (same level) -> next()
    $("table").find("#txt").parent().next().find(".txt:eq(1)").val(); // value2

    // when you want to find previous (same level) -> prev()
    $("table").find("#txt:eq(3)").prev().val(); // value2
  });
</script>
<body>
  <table>
    <tr>
      <td>
        <input type="text" id="txt" value="value"/>
      </td>
      <td>
        <input type="text" id="txt" value="value1"/>
        <input type="text" id="txt" value="value2"/>
        <input type="text" id="txt" value="value3"/>
        <input type="text" id="txt" value="value4"/>
      </td>
    </tr>
  </table>
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


