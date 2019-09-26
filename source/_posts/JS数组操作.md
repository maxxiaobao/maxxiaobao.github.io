---
title: JavaScript操作数组
tags: javascript
date: 2017-03-05 13:31
---

```
	一般用到的就是遍历数组取值完成数据渲染，突然发现不记得数组操作了~学！
```

> #### 1 数组的新建

```javascript
var arrayObj = new Array();　//创建一个数组
var arrayObj = new Array([size]);　//创建一个数组并指定长度，注意不是上限，是长度
var arrayObj = new Array([element0[, element1[, ...[, elementN]]]]);　//创建一个数组并赋值
```

第二种方法虽然指定了数组的长度，但数组的长度是可变的，指定了数组长度为 5，当存储 6 个元素时，数组长度即为 6。

<!-- more -->

> #### 2 数组元素的访问

```javascript
var testGetArrValue = arrayObj[i];  //获取元素的值
var arrObj[i] = "这是元素的值";    //给数组元素赋值
```

    i是数组的第（i+1）个元素，因为数组的下标是从0开始的

> #### 3 数组元素的添加

```javascript
arrObj.push(item);   //将元素添加到数组的尾部，返回新数组的长度
arrObj.unshift(item);   //将元素添加到数组的头部，其他元素后移，返回新数组的长度
arrObj.splice(index,howmany,item1,.....,itemX);  //index（必填）添加/删除元素的起始位置，howmany（必填）添加/删除元素的个数，item(选填)如果有则添加，没有就删除
```

> #### 4 数组元素的删除

```javascript
arrObj.pop(); //移除最后一个元素，返回被除元素的值
arrObj.shift(); //移除第一个元素，返回移除元素的值，其他元素前移
arrObj.splice(deletePos, deleteCount); //deletePos移除位置，deleteCount移除的数量，返以数组的形式回移除的元素
```

> #### 5 数组的截取与合并

```javascript
arrObj.slice(start, end); //以数组的形式返回从start到end的元素（不包括end），如果end不填则返回star后的所有元素
arrObj.concat(item); //arrObj与item合并为新的数组，item可以是元素、也可以是数组，返回合并后的新数组
```

> #### 6 数组的拷贝

```javascript
arrayObj.slice(0); //返回数组的拷贝数组，注意是一个新的数组，不是指向
arrayObj.concat(); //返回数组的拷贝数组，注意是一个新的数组，不是指向
```

> #### 7 数组的排序

```javascript
arrObj.reverse(); //数组反转，返回数组地址
arrObj.sort(); //数组元素排序，返回数组地址
```

> #### 8 数组元素字符串化

```javascript
arrayObj.join(separator); //返回字符串，这个字符串将数组的每一个元素值连接在一起，中间用 separator 隔开。
toLocaleString 、toString 、valueOf：可以看作是join的特殊用法，不常用
```

> #### 9 数组的三个属性

- length :数组元素的个数，数组的长度是可定义的，但它是可变的

- prototype :返回对象类型原型的引用。prototype 属性是 object 共有的。
  objectName.prototype
  objectName 参数是 object 对象的名称

- constructor :表示创建对象的函数。

```
文章参考https://blog.csdn.net/xcxinghai/article/details/13502583
```
