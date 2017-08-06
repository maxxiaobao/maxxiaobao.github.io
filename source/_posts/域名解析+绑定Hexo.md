---
title: 域名解析+绑定Hexo
date: 2016-04-07 12:36
tags: hexo
---

这两天折腾完了博客搭建好后，决定配一个名字~买域名时纠结买哪家买后缀是啥的，后来查了好久觉得这样丧失我本来写博客的意义了，选来选去觉得还是自己的名字最好！
对~就是 -- 字如其人 - 人如其名 - 的 - 马秀丽 - <a href="http://maxiuli.com">maxiuli.com</a>

#### 过程

* 购买域名
  我购买的<a href="https://wanwang.aliyun.com/">阿里云</a>，觉得接地气一点，国外的过程也不麻烦--<a href="https://sg.godaddy.com/">GoDaddy</a>、<a href="https://www.namecheap.com/">nameCheap</a>。

<!--more-->
* 将域名解析
  首先到运营商修改DNS服务器，就是箭头指的地方--<a href="https://support.dnspod.cn/Kb/showarticle/tsid/40/">修改方法</a>
  <img src="http://7xslws.com2.z0.glb.clouddn.com/type.png">
  下一步解析：
  我是用的<a href="https://www.dnspod.cn/">DNSPod</a>,解析步骤--<a href="https://support.dnspod.cn/Kb/showarticle/tsid/28/">帮助</a>
  重点是解析的时候，有几个地方需要注意。
  <img src="http://7xslws.com2.z0.glb.clouddn.com/QQ%E5%9B%BE%E7%89%8720160407130155.png">
  图片中的第一二行和最后一行使我们要添加的，记录值就是图中所示，最后一行的记录值是在GitHub上的地址。

* 同步到GitHub
    在本地的Hexo文件夹所在地，例如：E:/Hexo 在Hexo下source文件夹下新建文件CNAME，里面就写你的域名，例如：maxiuli.com
    然后执行
    ```
    hexo g
    hexo d
    ```
 这样就同步到了GitHub上，如果当时刷新不出来的话，耐心等个几分钟就OK啦~（我不停的喝水）

 <a href="#">预祝大家绑定成功~记得留言互访！(* ￣3)(ε￣ *)</a>