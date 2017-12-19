---
title: 如何创建一个NPM包
date: 2017-12-08 18:04:00
---

经常使用 `npm install` 命令安装各种包，这次自己尝试自己写了一个发布在npm上(其实这是第二个了)

### 什么是npm

> [npm](https://www.npmjs.com/) 是Node 的模块管理器，功能极其强大。 它是Node 获得成功的重要原因之一。 正因为有了npm，我们只要一行命令，就能安装别人写好的模块。

NPM [官方网站](https://www.npmjs.com/)
先来 [注册一个账号](https://www.npmjs.com/signup)

<!--more-->
### 写一个包

* 创建一个文件夹 `test`
* 创建一个 `index.js`

``` js
  // index.js
  function test() {
    console.log("Hello world !");
  }
  module.exports = test;
``` 

* 命令行 执行 `npm init` 创建 `package.json` （所创建的 `test` 的基本信息）

>   "name": "test",
  "version": "1.0.0",

### 上传到npm官网

* `npm adduser` 输入username 和 password

 使用 <b>test</b> 发布 会有error
> npm ERR publish 403.
 You do not have permission to publish 'test'.Are you logged in as the corrent user?:test

  意思是我没权限发布test，并问我是否使用了正确的账号
  说明test被人 发布过了，可以在`package.json`中 `name` 换一个，比如`test-mary`

* `npm publish` 上传到npm官网
*  如果对npm包做了修改后，需要在 `package.json` 的 `version` ，然后执行 `npm publish`
* `npm unpublish --force` 在npm上删除包

