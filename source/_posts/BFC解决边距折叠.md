---
title: BFC解决边距折叠
date: 2020-4-13 22:59
---

### 什么是边距折叠

当块级元素（block）的上外边距(margin-top)和下外边距(margin-bottom)同时都有设定时只会只会保留最大边距，这种行为称为外边距折叠（margin collapsing)。[查看官方文档](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing)

<!-- more -->

> 比如:
> margin-bottom: 40, margin-top: 20, 边距为正取大值，最后 两个元素之间边距 40
> margin-bottom: 40, margin-top: -20, 最后 两个元素之间边距 40 - 20 = 20
> margin-bottom: -40 margin-top: -20 边距为负取小值，最后 两个元素之间边距 -40

### BFC 解决边距折叠

BFC (block formatting context) 块级格式化 [文档](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Block_formatting_context)

何为 BFC ，只要元素满足下面任一条件即可触发 BFC 特性：

1. body 根元素 `<html>`
2. 浮动元素：float 不为 none 的属性值
3. 绝对定位：position: absolute 或 fixed
4. display 为： inline-block、table-cells、flex 、grid
5. overflow 除了 visible 以外的值 (hidden、auto、scroll)

BFC 的布局规则：

1. 内部的盒子会在垂直方向，一个个地放置；
2. BFC 是页面上的一个隔离的独立容器；
3. 属于同一个 BFC 的 两个相邻 Box 的 上下 margin 会发生重叠 ；
4. 计算 BFC 的高度时，浮动元素也参与计算
5. BFC 的区域不会与 float 重叠；

### BFC 还可以干什么

> 1. BFC 可以包含浮动的元素（清除浮动）

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="html,result" data-user="maxxiaobao" data-slug-hash="jObPQyz" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="clear-float">
  <span>See the Pen <a href="https://codepen.io/maxxiaobao/pen/jObPQyz">
  clear-float</a> by Mary (<a href="https://codepen.io/maxxiaobao">@maxxiaobao</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

> 2. 阻止元素被浮动元素覆盖

把 `overflow: hidden` 注释后，便可发现左侧的红盒子底下右侧 div 的灰色背景被覆盖。

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="html,result" data-user="maxxiaobao" data-slug-hash="JjYYMME" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="example2">
  <span>See the Pen <a href="https://codepen.io/maxxiaobao/pen/JjYYMME">
  example2</a> by Mary (<a href="https://codepen.io/maxxiaobao">@maxxiaobao</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>
