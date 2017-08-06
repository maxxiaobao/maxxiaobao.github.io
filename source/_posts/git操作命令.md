---
title: git命令操作
date: 2017-05-01 18:04:00
---

平时用的git命令就那么几个，都很简单，这几天系统的看了廖雪峰老师的教程，简直写的不能更好，这个记录比较简洁，推荐大家点击<a href="http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000">廖雪峰老师的git教程</a>

>git 命令

>> git init  初始化一个仓库

>> git add readme.text 仓库中条件一个文件

>> git commit -m "balabala" 仓库代码合并

>> git status 仓库的状态

>> git diff 仓库的变化

>> git log 打印日志

>> git reflog 查看原来的命令

<!-- more -->

>> stage 暂存区

>> git checkout -- (filename) 工作区的修改撤销

>> git reset HEAD (filename) 暂存区修改撤销 （再进行工作区撤销）

>> git reset --hard HEAD^ (num)回退到上一版本

>> git rm （filename）删除文件

>> git push  把本地仓库修改推送到远程仓库修改

>> git clone （url）将远程仓库的内容克隆到本地

>> git branch （devname）创建分支

>> git branch 查看所有分支

>> git checkout （devname）切换分支

>> git merge （devname）将dev分支上的东西合并到当前所在分支

>> git branch -d （devname）删除分支