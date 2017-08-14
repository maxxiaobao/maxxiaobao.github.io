---
title: firstChild和firstElementChild的区别
date: 2016-6-20 20:03
tags: javascript
---

在做百度前端学院任务二十二的时候遇到了一个问题，在遍历数组的时候发现节点找不到，后来对比别人的代码发现，是\*firstChild\*和\*firstElementChild\*在搞鬼~

 #### ·firstChild的用法

此属性用来获取指定元素的第一个子元素,如果元素不存在，则返回null

```语法
var childnNode = Node.firstChild
```

下面看例子
```
<div id="main">
		<span>这是第一个span标签</span>
		<span>这是最后一个span标签</span>
	</div>
	<div id="test"></div>
	<script type="text/javascript">
		var testnode = document.getElementById("test");
		var mainnode = document.getElementById("main"); 
		testnode.innerHTML = mainnode.firstChild;
		//testnode.innerHTML = testnode.innerHTML + mainnode.firstElementChild;
	</script>

```
<!--more-->
```显示结果
这是第一个span标签 这是最后一个span标签
[object Text]
```

此时获取到的是一个文本节点，以上代码，在不同的浏览器中也会有不同的结果，在标准浏览器中，获取到的为一个文本节点，但是再IE8 和IE8以下的版本，则会获取到span元素节点，因为标准浏览器会把空格和换行当作文本节点，而IE8 和IE8以下的版本则会直接忽略。

 #### ·firstElementChild的用法

此属性返回当前元素的第一个元素子节点，如果没有元素子节点，则返回null.

```语法结构
var childnNode = Node.firstElementChild
```
举例说明

```
<div id="main">
		<span>这是第一个span标签</span>
		<span>这是最后一个span标签</span>
	</div>
	<div id="test"></div>
	<script type="text/javascript">
		var testnode = document.getElementById("test");
		var mainnode = document.getElementById("main"); 
		//testnode.innerHTML = mainnode.firstChild;
		testnode.innerHTML =mainnode.firstElementChild;
	</script>
```
```
显示结果：
这是第一个span标签 这是最后一个span标签
[object HTMLSpanElement]
```
最终获取到的是span元素，这个应该更好理解。

> 浏览器兼容:
（1）.IE9和IE9以上浏览器支持此属性。
（2）.谷歌浏览器支持此属性。
（3）.火狐浏览器支持此属性。
（4）.opera浏览器支持此属性。
（5）.safria浏览器支持此属性。


 #### ·对比总结
  
  （1）共同点都是获取父节点下的第一个节点对象。
  （2）但是firstElementChild更傲娇，直接忽略文本节点（包括空格、回车）

  文章参考：http://www.softwhy.com/forum.php?mod=viewthread&tid=18854