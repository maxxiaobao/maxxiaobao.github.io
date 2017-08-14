---
title: 神奇的 inline-block
date: 2017-8-13 14:01
tags: javascript
---

```
突然发现inline-block真是个神奇的属性呢~
```

##### 当写下下面的代码的时候

``` html
<style>
    .div1{
        width: 200px;
        height: 200px;
        display: inline-block;
        background-color: #F98E90;
    }
    .div2{
        width: 200px;
        height: 200px;
        display: inline-block;
        background-color: #B9D7EA;
    }
</style>
<div class="div1"></div>
<div class="div2"></div>
```
<!-- more -->
##### 你会看到下面的两个彩色块（自古红蓝出CP）
<div style="width: 200px;
            height:200px;
            display:inline-block;
            background-color:#F98E90;"></div><div style="width: 200px;
            height: 200px;
            display: inline-block;
            background-color: #B9D7EA;"></div>

##### 当我给红色块加点文字时
<div style="width: 200px;
            height:200px;
            color:#fff;
            display:inline-block;
            background-color:#F98E90;">我是一个有文字的红色块</div><div style="width: 200px;
            height: 200px;
            display: inline-block;
            background-color: #B9D7EA;"></div>

##### 两个div块都添加文字
<div style="width: 200px;
            height:200px;
            color:#fff;
            display:inline-block;
            background-color:#F98E90;">我是一个有文字的红色块</div><div style="width: 200px;
            height: 200px;
            display: inline-block;
            background-color: #B9D7EA;">我也有文字！！！</div>

##### 咦~~~

发现只有红色div有文字时它会下沉，其实它们对于文字有一个基线，默认是在父元素的基线（baseline）,可以通过修改`vertical-align`来修改基线位置,下面是`vertical-align:top`
<div style="width: 200px;
            height:200px;
            color:#fff;
            display:inline-block;
            vertical-align:top;
            background-color:#F98E90;">我是一个有文字的红色块</div><div style="width: 200px;
            height: 200px;
            display: inline-block;
            background-color: #B9D7EA;"></div>

> 其实还是没有真正的明白基线是什么东西。


