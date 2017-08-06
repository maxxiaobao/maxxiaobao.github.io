---
title: 如何使json的key值是变量
date: 2017-4-22 14:45:14
tags: javascript
---

> var stu = {};
> var attr = "name"
> stu.attr = "mary"  // stu = {attr: "mary"}
> var stu[attr] = "mary"; // stu = {name: "mary"}

###### 如果看到这里看明白了下边就不用看了。恩

<!--more-->

首先，json是什么呢？

JSON(JavaScript Object Notation, JS 对象标记) 是一种轻量级的数据交换格式。它基于 ECMAScript 规范的一个子集，采用完全独立于编程语言的文本格式来存储和表示数据。简洁和清晰的层次结构使得 JSON 成为理想的数据交换语言。易于人阅读和编写，同时也易于机器解析和生成，并有效地提升网络传输效率。

#### ·JSON语法规则

在 JS 语言中，一切都是对象。因此，任何支持的类型都可以通过 JSON 来表示，例如字符串、数字、对象、数组等。但是对象和数组是比较特殊且常用的两种类型：
* 对象表示为键值对
* 数据由逗号分隔
* 花括号保存对象
* 方括号保存数组

举个栗子

``` javascript
var stu = {"firstName": "John"}
var stu = {firstName = "John"}
```

#### ·JSON与JS对象的关系

JSON是JS对象的字符串表示法，它使用文本表示一个JS对象的信息，本质是一个字符串。

``` javascript
var obj = {a: 'Hello', b: 'World'}; //这是一个对象，注意键名也是可以使用引号包裹的
var json = '{"a": "Hello", "b": "World"}'; //这是一个 JSON 字符串，本质是一个字符串
//对象转为和JSON字符串
var json = JSON.stringify({a: 'Hello', b: 'World'}); //结果是 '{"a": "Hello", "b": "World"}'
//JSON字符串转换为对象
var obj = JSON.parse('{"a": "Hello", "b": "World"}'); //结果是 {a: 'Hello', b: 'World'}
```

#### ·JSON属性获取和设置

```
var stu = {name: "mary",age:18};  //创建一个学生对象
console.log(stu.name); //输出学生的姓名 用'.'获取属性
stu.age = 19;  //第二年学生长了一岁
console.log(stu.age);  //这时输出19
var teacher = {}; //新建一个老师
teacher.name = "jack"; //虽然原来没有名字，但直接写就可以
// !!!
console.log(teacher['name']);  //其实这样也是可以的 [] 中括号里为属性名称
```

总结就是获取属性用'.'或者'[]'来获取属性的值~是不是感觉'[]'不如'.'跟方便，其实中括号还有个很有用的地方，这才是今天的重点~

铛-铛-铛- 敲黑板~

现在问题来了，学生的属性已知的，但如果是变量呢~？例如下面这样

```
var stu = {};
var attr1 = "name";
var attr2 = "age";
stu.attr1 = "mary";
stu.attr2 = 18;
console.log(stu);
```

这段代码放到控制台你会发现输出是这样的 {attr1: "mary", attr2: 18}
它根本不把"name","age"放在眼里，那我们的应该怎么办呢?
这样中括号就派上用场了

```
var stu = {};
var attr1 = "name";
var attr2 = "age";
stu[attr1] = "mary";
stu[attr2] = 18;
console.log(stu);
```

这样在控制台输出的将会是{name: "mary", age: 18}

```
var stu = {};
var attr1 = "name";
var attr2 = "age";
stu['attr1'] = "mary";
stu['attr2'] = 18;
console.log(stu);
```

如果这样呢？又打回原形了~{attr1: "mary", attr2: 18}
所以，这样就容易明白了，attr1不加引号为变量，如果加引号将会视为字符串，那就和上边'.'一样了

其实最后这两段代码才是我想说的重点，如何在key值是变量的时候操作json，但写的时候发现，直接写很突兀，就顺带复习一下这么多~有的资料是在百度百科上找到，有的是自己举得例子，有不正确的地方大家告诉我喔~邮箱：<a>maxiuli95@Gmail.com</a>