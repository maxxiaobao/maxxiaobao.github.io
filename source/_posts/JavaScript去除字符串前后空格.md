---
title: JS去除字符串前后空格
date: 2016-5-2
tags: JavaScript
---

在获取到字符串是经常出现前后有空格或换行等空白（在字符串匹配时是个大坑）
利用下面的方法就可以去除字符串前后的空格啦~
用正则找到空白符，然后使用 replace()方法将空白符替换掉

```
function trimStr(str)
{return str.replace(/(^\s*)|(\s*$)/g,"");}
```

<!--more-->

关于正则表达式的使用给大家个参考：https://deerchao.net/tutorials/regex/regex.htm
