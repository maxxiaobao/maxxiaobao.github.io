---
title: JavaScript实现文本框显示行号
tags: JavaScript
date: 2016-4-6 20:03
---

#### 如下图所示，用此布局

<img src="https://7xslws.com1.z0.glb.clouddn.com/textarea2.png">
#### Body部分主要内容
```HTML
<div id="box">     // div ---> ③
	<div id="line"></div>    // div ---> ①
	<textarea id="textarea" rows="5" cols="40"></textarea>   // div ---> ②
</div>
```
<!-- more -->

#### css 样式设置

```CSS
	*{
	margin: 0;
	padding: 0;
	}
	#box{
		height: 100px;
		margin-left: 40%;
		margin-top: 20%;
	}
	#line{
		width: 20px;
		height: 100px;     /* !!! ①的高度 */
		float: left;
		background-color: #ccc;
		overflow: hidden;
	}
	#textarea{
		border-left: none;
		line-height: 20px;
		height: 98px;      /* !!! ②的高度，因为边框所以 -2 */
	}
	.row{                 /* 显示行数的div */
		color: #999;
		text-align: center;
		width: 20px;
		font-size: 15px;
		height: 20px;
	}
```

#### JavaScript 实现部分

```Javascript
<script type="text/javascript">
		window.onload = function () {
			var textArea = document.getElementById("textarea");

			addHandler(textArea,'keyup',function(){
				onKeyUp(textArea);
			});

			addHandler(textArea,'scroll',function(){
				onScrollChange(textArea);
			})
		}
		//键盘点一下就判断换行情况
		function onKeyUp(textArea){
			var line = document.getElementById("line");
			line.innerHTML = "";
			var text = textArea.value.split("\n");
			for(var i=0;i<text.length;i++){
				var row = document.createElement("div");
				if(i==0){
					row.id = "fir";
				}
				row.className = "row";
				row.innerHTML = i+1;
				line.appendChild(row);
			}
			document.getElementById("fir").style.marginTop = -textArea.scrollTop + "px";
		}
		//文本框滚动条滚动行号也跟着滚动
		function onScrollChange(textArea){
			document.getElementById("fir").style.marginTop = -textArea.scrollTop + "px";
		}
		//考虑浏览器事件添加
		function addHandler(element,type,handler){
			if(element.addEventLister){
				element.addEventLister(type,handler,false);
			}else if(element.attachEvent){
				element.attachEvent('on'+type,handler);
			}else {
				element['on'+type] = handler;
			}
		}
```

#### 总结

在百度前端学院任务 35 时需要完成这样一个效果，开始时觉得很难，真正做时发现不是任务难，是思路不清晰和基础不牢固。

开始判断行数时想的是`change`，如果 textarea 改变了就判断有几个换行，这时才知道，当 textarea 失去焦点的情况下和上一次的改变了才叫改变，于是看别人的方法才知道用`keyup`，键盘抬起时就判断一次，当时学习 keyup 的时候根本没想到它是这么用。

在添加行数 div 时超出容器会溢出在外显示，对`overflow`属性在任务一时学习过，现在再重温一遍
`visible`:(默认值)内容不会被修剪，会呈现在元素框之外
`hidden`:内容会被修剪，并且其余内容不可见
`scroll`:如果内容被修剪，并且其余内容不可见，会显示滚动条
`auto`:如果内容被修剪，并且其余内容不可见，会显示滚动条
`inherit`:指定从父元素继承 overflow 实行的值

然后问题又出现了，当滚动 textarea 时行数时不变的，并且行数的 div 是没有 scroll 的，利用 textarea 的值 scrollTop 值<strong>(滚动到上方被隐藏内容到高度)</strong>,设置行数的 div 也被隐藏这么多<strong>(第一行 div.style.marginTop = -(top)+"px";)</strong>

这样就差不多了，我天真的以为可以了，开始时用的 chrome，于是用 IE 和 firefox 测试了下，这是什么鬼！（我一直不太注意浏览器的兼容性问题）
原来同样的标签，在不同浏览器的大小、长相都不一样
浏览器添加事件方法不同，这个封装好每次直接用就可以了
三个浏览器对比图

---

#### 谷歌

<img src="https://7xslws.com1.z0.glb.clouddn.com/Googletest.png">
* * *
#### IE
<img src="https://7xslws.com1.z0.glb.clouddn.com/ietest.png">
* * *
#### firefox
<img src="https://7xslws.com1.z0.glb.clouddn.com/firefoxtest.png">

> 越来越发现：
> 知道了是一回事，会用是一回事
> 技巧不是学来的，是自己总结的

当初学 JavaScript 里的函数时没有觉得有多难，在网上做一个小练习，感觉自己就会了，等真正在实践中用到的时候，发现对那个方法根本没有真正的学会。
