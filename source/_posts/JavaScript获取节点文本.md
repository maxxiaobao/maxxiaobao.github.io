---
title: JS获取节点文本
date: 2016-4-26 20:03
tags: JavaScript
---

在做任务二十三时，要获取每个 Div 里的文本，只获取是儿子节点的文本节点。
例如：只获取“apple”

于是总结了获取节点中文本内容的方法：

以以下代码为例

```
<div id="main">
	apple
	<div>orange</div>
	<div>banana</div>
</div>
<input type="text" id="text" value="文本">
```

第一种：

```
var text = document.getElementById("main").innerHTML;
```

这样获取到的是#main 盒子里的所有内容，如图所示
<img src="https://7xslws.com2.z0.glb.clouddn.com/1.png">

第二种

```
var text = document.getElementById("main").innerText;
```

<!--more-->

这样获取到是#main 盒子里的所有文本内容，但不包含标签，如图所示
<img src="https://7xslws.com2.z0.glb.clouddn.com/2.png">

第三种

```
var text = document.getElementById("main").firstChild.nodeValue;
```

这样是获取到#main 中的第一个文本节点的内容，如图所示
<img src="https://7xslws.com2.z0.glb.clouddn.com/3.1.png">
如果是使用<strong>firstElementChild</strong>，则是获取第一个元素节点里的文本内容
firstChild 和 firstElementChild 是不同的，可以查看<a href="https://maxiuli.com/2016/04/12/firstChild%E5%92%8CfirstElementChild%E7%9A%84%E5%8C%BA%E5%88%AB/">不同</a>

```
var text = document.getElementById("main").firstElementChild.innerHTML;
```

如图所示
<img src="https://7xslws.com2.z0.glb.clouddn.com/3.2.png">
第四种

```
var text = document.getElementById("text").value;
```

对于文本框，用 value 值来获取，value 可以不初始化，在文本框中最终输入的内容就是 value 值。如图所示
<img src="https://7xslws.com2.z0.glb.clouddn.com/4.png">
