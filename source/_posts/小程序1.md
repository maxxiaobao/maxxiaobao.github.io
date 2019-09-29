---
title: '小程序:修改上一页面的data'
date: 2019-09-23 20:35:36
tags:
---

为什么要修改上一页面的 data 呢？

遇到一个问题：
有一个页面 A, A 中有表单，其中有个字段要到 B 页面去填，填好后渲染在 A 页面，因为 B 里的字段由 A 里的状态控制是否保存到 store，所以暂时不放到 全局的 store 里，其实也可以为 B 里的字段创建个临时值，但我们可以在返回 A 页面时，手动修改上一页的 data.

<!--more-->

其实小程序的 `getCurrentPages()` 得到的数组里都是一个一个的 Page 对象，通过 Console 你就会发现可以拿到 Page 的属性以及方法，这样就可以用 setData 的方法了。

```
const pages = getCurrentPages();
const prevPage = pages[pages.length -1];
prevPage.setData({ valueB: 'valueB'})
```
