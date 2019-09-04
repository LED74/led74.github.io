---
layout: post
title: "plugin(tablednd)"
subtitle: "plugin(tablednd)"
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
<style>
	.blueStyle {
		background-color : blue;
		color : white;
	}
</style>
<script type="text/javascript" src="/jquery/jquery-1.12.4.min.js"></script>
<script type="text/javascript" src="/jquery/jquery.tablednd.1.0.3.min.js"></script>
<script type="text/javascript">
	$(function(){
		$("table").tableDnD({
			// When you drag an item, the item have a .bluestyle css
			onDragClass : 'blueStyle',
			// When you start drag
			onDragStart : function(table,row){
				console.log("start drag");
			},
			// When you stop drag
			onDragStop : function(table,row){
				// table number is be sorted
				$("table").find("tr").each(function(index,data){
					$(this).find("td").eq(0).html(index+1);
				})
				console.log("stop drag");
			}
		}); 
	})
</script>
</head>

<body>
<table>
<body>
	<table  border = "1">
		<tr>
			<td>
				1
			</td>
			<td>
				first
			</td>
			<td>
				first title
			</td>
		</tr>
		<tr>
			<td>
				2
			</td>
			<td>
				secound
			</td>
			<td>
				second title
			</td>
		</tr>
		<tr>
			<td>
				3
			</td>
			<td>
				third
			</td>
			<td>
				third title
			</td>
		</tr>
		<tr>
			<td>
				4
			</td>
			<td>
				fourth
			</td>
			<td>
				fourth title
			</td>
		</tr>
	</table>
</body>
</table>
</body>

</html>
```