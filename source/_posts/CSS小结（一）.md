---
title: CSS 小结（一）
date: 2018-5-7 20:17
tags: CSS
---

看了这个网站后 https://atomiks.github.io/30-seconds-of-css 做了个总结，把常用的记下了，很好的网站！

### CSS 选择器
``` css
li:not(:last-child) /* 除最后一个子元素外的其他元素 */
li:last-child /* 最后一个子元素 */
/* 第一个子元素 (last-child => first-child) */
```

### 三角形 triangle
``` html
<div class="triangle"></div>
<style>
  .triangle{
      width: 0;
      height: 0;
      border-top: 20px solid #ccc;
      border-left: 20px solid transparent;
      border-right: 20px solid transparent;
  }
</style>
```
<!-- more -->
例子 => <div class="triangle"></div>
<style>
  .triangle{
      display: inline-block;
      width: 0;
      height: 0;
      border-top: 20px solid #ccc;
      border-left: 20px solid transparent;
      border-right: 20px solid transparent;
  }
</style>

> 哪个方向的三角形则 则对面那条边有颜色


 ### 文字过长显示省略号

``` css
.truncate-text {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
  width: 200px;
}
```

### 利用伪元素清除浮动 Clearfix
``` html
<div class="clearfix">
  <div class="floated">float a</div>
  <div class="floated">float b</div>
  <div class="floated">float c</div>
</div>
<style>
  .floated{
    float: left;
  }
  .clearfix::after{
    content: '',
    display: block;
    clear: both;
  }
</style>
```

### 正方形 Constant width to height ratio

``` html
<div class="square"></div>
<style>
  .square{
    width: 10%;
    background: #ccc;
  }
  .square::before{
    content: '';
    float: left;
    padding-top: 100%;
  }
  .square::after{
    content: '';
    display: block;
    clear: both;
  }
</style>
```
> 对于宽度或高度大小已知的情况下是很容易画一个正方形的，这个对于宽度是比例（自适应）的时候，很实用。

### 文字选中样式 Custom text selection

``` html
<p class="custom-text-selection">Select some of this text.</p>
<style>
  .custom-text-selection::selection {
    background: deeppink;
    color: white;
  }
</style>
```
<p class="custom-text-selection"> >Select some of this text.</p>
<style>
  .custom-text-selection::selection {
    background: deeppink;
    color: white;
  }
</style>

### 禁止选择 Disable selection
``` html
<p class="unselectable">You can select me.</p>
<style>
  .unselectable{
    user-select: none;
  }
</style>
```
下面这段话无法选中👇
<p class="unselectable">You can select me.</p>
<style>
  .unselectable{
    user-select: none;
  }
</style>

> 可以禁止用户选中，但不是防止用户复制文本的安全方法。

### 加载 Donut spinner
```html
<div class="donut"></div>
<style>
  @keyframes donut-spin{
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: retate(360deg);
    }
  }
  .donut{
    display: inline-block;
    border: 4px solid rgba(0, 0, 0, 0.1);
    border-left-color: #7983ff;
    border-radius: 50%;
    width: 30px;
    height: 30px;
    animation: donut-spin 1.2s linear infinite;
    /* animation: donut-spin 1.2s linear infinite; */
    /* donut-spin => 动画名称 1.2s => 完成一次需要的时间  */
    /* linear => 动画保持匀速 infinite => 无限循环 */
  }
</style>
```
<div class="donut"></div>
<style>
  @keyframes donut-spin{
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
  .donut{
    display: inline-block;
    border: 4px solid rgba(0, 0, 0, 0.1);
    border-left-color: #7983ff;
    border-radius: 50%;
    width: 30px;
    height: 30px;
    animation: donut-spin 1.2s linear infinite;
  }
</style>

### 均匀分布 Evenly distributed children
``` html
<div class="evenly-distributed-children">
  <p>Item1</p>
  <p>Item2</p>
  <p>Item3</p>
</div>
<style>
  .evenly-distributed-children {
    display: flex;
    justify-content: space-between;
  }
</style>
```
<div class="evenly-distributed-children">
  <p>Item1</p>
  <p>Item2</p>
  <p>Item3</p>
</div>
<style>
  .evenly-distributed-children {
    background: pink;
    display: flex;
    justify-content: space-between;
  }
</style>

### 水平+垂直 居中 Flexbox centering

```html
<div class="flexbox-centering">
  <div class="child">Centered content.</div>
</div>
<style>
  .flexbox-centering {
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
```

### Hover事件下划线动画 Hover underline animation
``` html
<p class="hover-underline-animation">
  Hover this text to see the effect!
</p> 
<style>
  .hover-underline-animation {
    display: inline-block;
    position: relative;
    color: #0087ca;
  }
  .hover-underline-animation::after{
    content: '';
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 2px;
    transform: scaleX(0);
    background-color: #0087ca;
    transform-origin: bottom left;
    transition: transform .2s ease-out;
  }
  .hover-underline-animation:hover::after{
    transform: scaleX(1);
  }
</style>
```
<p class="hover-underline-animation">
  Hover this text to see the effect!
</p> 
<style>
  .hover-underline-animation {
    display: inline-block;
    position: relative;
    color: #0087ca;
  }
  .hover-underline-animation::after{
    content: '';
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 2px;
    transform: scaleX(0);
    background-color: #0087ca;
    transform-origin: bottom left;
    transition: transform .2s ease-out;
  }
  .hover-underline-animation:hover::after{
    transform: scaleX(1);
  }
</style>