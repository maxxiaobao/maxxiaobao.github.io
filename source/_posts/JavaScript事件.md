---
title: JavaScript事件大全
tags: JavaScript
---
> #### 一般事件

<ul>
	<li><strong>onClick——</strong>鼠标点击事件，多用在某个对象控制的范围内的鼠标点击</li>
	<li><strong>onDblClick——</strong>鼠标双击事件</li>
	<li><strong>onMouseDown——</strong>鼠标上的按钮被按下了</li>
	<li><strong>onMouseUp——</strong>鼠标按下后，松开时激发的事件</li>
	<li><strong>onMouseOver——</strong>当鼠标移动到某对象范围的上方时触发的事件</li>
	<li><strong>onMouseMove——</strong>鼠标移动时触发的事件</li>
	<li><strong>onMouseOut——</strong>当鼠标离开某对象范围时触发的事件</li>
	<li><strong>onKeyPress——</strong>当键盘上的某个键被按下并且释放时触发的事件.[注意:页面内必须有被聚焦的对象]</li>
	<li><strong>onKeyDown——</strong>当键盘上某个按键被按下时触发的事件[注意:页面内必须有被聚焦的对象]</li>
	<li><strong>onKeyUp——</strong>当键盘上某个按键被按放开时触发的事件[注意:页面内必须有被聚焦的对象]</li>
</ul>
<!--more-->
> #### 页面相关事件

<ul>
	<li><strong>onAbort——</strong>图片在下载时被用户中断</li>
	<li><strong>onBeforeUnload——</strong>当前页面的内容将要被改变时触发的事件</li>
	<li><strong>onError——</strong>捕抓当前页面因为某种原因而出现的错误，如脚本错误与外部数据引用的错误</li>
	<li><strong>onLoad——</strong>页面内空完成传送到浏览器时触发的事件，包括外部文件引入完成</li>
	<li><strong>onMove——</strong>浏览器的窗口被移动时触发的事件</li>
	<li><strong>onResize——</strong>当浏览器的窗口大小被改变时触发的事件</li>
	<li><strong>onScroll——</strong>浏览器的滚动条位置发生变化时触发的事件</li>
	<li><strong>onStop——</strong>浏览器的停止按钮被按下时触发的事件或者正在下载的文件被中断</li>
	<li><strong>onReset——</strong>当表单中RESET的属性被激发时触发的事件</li>
	<li><strong>onSubmit——</strong>一个表单被递交时触发的事件</li>
</ul>

> #### 表单相关事件

<ul>
	<li><strong>onBlur——</strong>当前元素失去焦点时触发的事件 [鼠标与键盘的触发均可]</li>
	<li><strong>onChange——</strong>当前元素失去焦点并且元素的内容发生改变而触发的事件 [鼠标与键盘的触发均可]</li>
	<li><strong>onFocus——</strong>当某个元素获得焦点时触发的事件</li>
</ul>

> #### 滚动字幕事件

<li><strong>onBounce——</strong>在Marquee内的内容移动至Marquee显示范围之外时触发的事件</li>
<li><strong>onFinish——</strong>当Marquee元素完成需要显示的内容后触发的事件</li>
<li><strong>onStart——</strong>当Marquee元素开始显示内容时触发的事件</li>

> #### 编辑事件

<ul>
	<li><strong>onBeforeCopy——</strong>当页面当前的被选择内容将要复制到浏览者系统的剪贴板前触发的事件</li>
 	<li><strong>onBeforeCut——</strong>当页面中的一部分或者全部的内容将被移离当前页面[剪贴]并移动到浏览者的系统剪</li>
</ul>

> #### 数据绑定

<ul>
	<li><strong>onAfterUpdate——</strong>当数据完成由数据源到对象的传送时触发的事件</li>
	<li><strong>onCellChange——</strong>当数据来源发生变化时</li>
	<li><strong>onDataAvailable——</strong>当数据接收完成时触发事件</li>
	<li><strong>onDatasetChanged——</strong>数据在数据源发生变化时触发的事件</li>
</ul>


> #### 外部事件

<ul>
	<li><strong>onAfterPrint——</strong>当文档被打印后触发的事件</li>
	<li><strong>onBeforePrint——</strong>当文档即将打印时触发的事件</li>
	<li><strong>onFilterChange——</strong>当某个对象的滤镜效果发生变化时触发的事件</li>
	<li><strong>onPropertyChange——</strong>当对象的属性之一发生变化时触发的事件</li>
	<li><strong>onReadyStateChange——</strong>当对象的初始化属性值发生变化时触发</li>
</ul>

<h6>突然发现经常用到触发事件，就总结了一下~<a href="http://www.jb51.net/article/28772.htm">文章参考</a></h6>

