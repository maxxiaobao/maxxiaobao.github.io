---
title: js控制audio音频的播放与暂停
date: 2017-5-4 20:03
tags: javascript
---

上周的时候，需要做一个音频列表，后边有播放和暂停控制，真正的audio标签其实是不显示的，所以就要用js控制audio标签。

首先你要知道什么是audio标签<a href="http://www.w3school.com.cn/html5/html5_audio.asp" title="">关于audio</a>，先上代码
``` html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		.playSpan{
			color: #9DE3FE;
		}
		.stopSpan{
			color: #FF3366;
		}
	</style>
</head>
<body>
	<!-- 建一个audio标签 -->
	<audio id="audio" controls="controls" src="http://www.w3school.com.cn/i/horse.ogg"></audio>
	<!-- span标签控制音频 -->
	<span class="playSpan" onclick="play()">播放</span>
	<script>
		function play(){
			var audio = document.getElementById("audio");
			var span = document.getElementsByTagName("span")[0];
			if(span.className == "playSpan"){
				audio.play();
				span.innerText = "暂停";
				span.className = "stopSpan"; 
				/*  监听音频播放完成  */
				audio.addEventListener('ended', function () {  
	   				span.innerText = "播放";
					span.className = "playSpan"; 
				}, false);
			}else{
				audio.pause();
				span.innerText = "播放";
				span.className = "playSpan"; 
			}
		}
	</script>
</body>
</html>
```
<!--more-->

> 其实重点就是那几个方法
>> audio.play()  音频播放
>> audio.pause()  音频暂停
>> audio 的 ended 视频停止
>> audio.currentTime  音频播放时间

#### 这个地方有个重点就是上边的方法都标签的原生方法，所以当你使用jQuery拿到标签时，要把jQuery对象转成DOM元素，这样才能调用原生方法~

 没做的时候觉得很难，做了发现audio也只是和普通的标签，按常理做就好了，恩~。