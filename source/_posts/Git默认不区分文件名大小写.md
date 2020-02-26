---
title: "Git: 默认不区分文件名大小写"
date: 2020-2-26 21:08
---

（天哪，马上要 2020 年 3 月份了，太快了）

又遇到这个问题了，这是个什么问题呢？

### 问题

你的 repo 里有一个文件叫 `myname.js`, 后来改名 `MyName.js`

修改后准备提交，命令行输入

```
git status
```

发现并没有什么改动可以提交

<!-- More -->

### 原因

Git 里默认对于文件名大小写是不敏感的
命令行输入，查看当前的设置

```
git config core.ignorecase
```

`true` 则是不敏感

### 解决

打开终端，输入以下命令配置 Git 使其对文件名大小写敏感

`git config core.ignorecase false`

设置完成后，再修改，可以看到自己的改动

但如果这时直接提交就会出现另外一个问题，本地是把文件 `myname.js` 修改为 `MyName.js`

可是提交后的远程仓库 `myname.js` 和 `MyName.js` 同时存在，`myname.js` 并没有被删除

（非常之坑）

所以意味着修改的时候要删除之前的文件, 修改名字后

```
git add MyName.js
git rm myname.js
git commit -m 'rename ...'
git push
```

很麻烦是不是，是的

讲了半天，其实 Git 可以直接修改文件名，然后提交

```
git mv oldfile(旧文件名) newfile(新文件名)
```

> 详情查看 [https://git-scm.com/docs/git-mv](https://git-scm.com/docs/git-mv)
