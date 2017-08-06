---
title: MapHashMap 获取Key值的方法
date:  2015-12-25 18:54
tag: Java
---

1、通过  KeySet()方法
```
Map<String,Student> newmap = new HashMap<String,Student>();       //newmap HaspMap类型的集合  有唯一的Key，一个Key对应相应的学生

Student stu = new Student("11","Mary","79");                     //创建一个学生对象 学号11; 姓名 Mary 成绩 79  

newmap.put("1101",stu);                                         // Mary 同学对应唯一的编号 11，11即为它的Key值

Set set = newmap.KeySet();                                      //利用Set()函数获取newmap中所有的key值

Iterator  ite = set.iterator();                               // 创建一个叫ite的迭代器

while(ite.hasNext()){                                         // 利用hasNext()判断下一个元素是否存在
    System.our.println((String)ite.Next());                //  !这句才是重点 获取到Key值后要进行强制类型转换才能输出  
    newmap.get(ite.Next()).showStudent();              //  Next() 第一次调用时返回的是newmap里的第一个元素的key值，下次调用返回下一个元素的key值
}
```
<!--more-->
2、通过 entry.set() 方法

```
HashMap map;
Iterator i = map.entrySet().iterator();
while (i.hasNext()) {
Object obj = i.next();
String key = obj.toString();
}
// or
while (i.hasNext()) {
Entry entry = (java.util.Map.Entry)it.next();
entry.getkey();
entry.getValue();
}
```