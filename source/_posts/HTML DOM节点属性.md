---
title: HTML DOM节点属性
date: 2016-5-27 20:03
tags: HTML
---

<b>在 HTML DOM 中，所有的事物都是节点。DOM 是被视为节点树的 HTML</b>

#### 为什么说是 DOM 节点树呢~？看图

<img src="https://7xslws.com2.z0.glb.clouddn.com/domtree.png">

其实很好理解就是根上有树干，树干上有树枝，树枝再生树枝，但这是一个<b>倒过来的树</b>

#### 根据 W3C 得 HTML DOM 标准，HTML 文档中所有内容都是节点

<ul>
	<li>整个文档是一个文档节点</li>
	<li>每个HTML元素都是元素节点</li>
	<li>HTML元素里的文本是文本节点</li>
	<li>每个HTML属性是属性节点</li>
	<li>注释是注释节点</li>
</ul>

<!--more-->

### 节点的属性

> <b> innerHTML 属性</b>

> > 这个就是获取元素的内容，比较好理解，可以查看之前写的<a href="https://maxiuli.com/2016/04/15/JavaScript%E8%8E%B7%E5%8F%96%E8%8A%82%E7%82%B9%E6%96%87%E6%9C%AC/">JS 获取节点文本</a>对比理解

> <b>nodeName 属性</b>

> > nodeName 属性规定节点的名称.
> > nodeName 是只读的
> > 元素节点的 nodeName 与标签名相同
> > 属性节点的 nodeName 与属性名相同
> > 文本节点的 nodeName 始终是 #text
> > 文档节点的 nodeName 始终是#document

> <b>nodeValue 属性</b>

> > nodeValue 属性规定节点的值
> > 元素节点的 nodeValue 是 undefi 或 null
> > 文本节点的 nodeValue 是文本本身
> > 属性节点的 nodeValue 是属性值

> <b>nodeType 属性</b>

> > 元素类型 ---> NodeType
> > &nbsp;&nbsp;元素&nbsp;&nbsp;--->1
> > &nbsp;&nbsp;属性&nbsp;&nbsp;--->2
> > &nbsp;&nbsp;文本&nbsp;&nbsp;--->3
> > &nbsp;&nbsp;注释&nbsp;&nbsp;--->8
> > &nbsp;&nbsp;文档&nbsp;&nbsp;--->9

### 举个栗子

```
//整个文档是个文档节点
<html>
  <head>  // 在<html>里的标签元素都是元素节点
    <title>DOM 节点</title>
    //<title>是一个元素节点，“DOM节点”是文本节点
  </head>
  <body>
    <h1>DOM 第一课</h1>
    <a href="https://maxiuli.com">我的博客</a>
    //<a>是一个元素节点，“我的博客”是文本节点，href是属性节点
  </body>
</html>

```

<p color="">文章是找资料自己写的，有不对的地方请指正~maxiuli95@Gmail.com</p>
