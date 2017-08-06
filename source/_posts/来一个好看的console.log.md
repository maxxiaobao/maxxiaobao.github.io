---
title: 来一个好看的console.log
---

每天都在console.log(),在debug的时候确实很好用，无意间在爱奇艺F12了一下，发现原来console还可以有样式的~? 刚给域名续了两年（比收到刚买的包包还开心），接下来看看好看的log吧~


----------------------------------------------------先来一条分割线-----------------------------------------------------------------

 ```
 console.log(data);
 ```
 一般的我们是这样写的,data一般是个变量或者是个其他什么值，写法简单，打印出来也很简单，他是这样子的

<img src="http://7xslws.com1.z0.glb.clouddn.com/img1.png" alt="">

那么加样式应该怎么写呢？

<!-- more -->

举个栗子

```
console.log("%c我有样式了", "color: red");
```
看图就可能更明了了

<img src="http://7xslws.com1.z0.glb.clouddn.com/img2.png" alt="">

所以说要识别文字要在前边加一个%c，这样才知道前边是文字，后边是样式

接下来

你可能会问

我每个字的样式不一样的那怎么办呢

哈哈哈哈哈哈

我就知道你会这么问

看代码

```
console.log("%c我有样式了 %c我有样式吗？","color: red");
console.log("%c我有样式了 %c我有样式吗？","color: red","color: green");
console.log("%c我有样式了 %c我有样式吗？%c必须的有样式啊","color: red","color: green","color: yellow");
```
看图

<img src="http://7xslws.com1.z0.glb.clouddn.com/img3.png" alt="">

所以说有几个样式就对应几个%c，没有样式了，%c也就被认为是普通字符了

还有这个

```
console.log('%c彩色文字啊 ', 'background-image:-webkit-gradient( linear, left top, right top, color-stop(0, #f22), color-stop(0.15, #f2f), color-stop(0.3, #22f), color-stop(0.45, #2ff), color-stop(0.6, #2f2),color-stop(0.75, #2f2), color-stop(0.9, #ff2), color-stop(1, #f22) );color:transparent;-webkit-background-clip: text;font-size:5em;');
```

比较有趣的console <a href="https://www.zhihu.com/question/28831274" title="">https://www.zhihu.com/question/28831274</a>(他们是怎么找到的？恩？)

可以看下console的API<a href="http://getfirebug.com/wiki/index.php/Console.log">http://getfirebug.com/wiki/index.php/Console.log</a>
还有这个<a href="http://www.css88.com/archives/3678" title="">http://www.css88.com/archives/3678</a>
