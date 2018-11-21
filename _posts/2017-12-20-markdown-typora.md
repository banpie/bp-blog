---
ID: 410
post_title: >
  比 Markdown Here
  更惊人的微信公众号发布指南出炉
post_name: markdown-typora
author: banpie
post_date: 2017-12-20 00:00:00
layout: post
link: http://www.xgclass.cn/markdown-typora/
published: true
tags: [ ]
categories:
  - 工具
---
> 本文适用任何水平、在任何平台写作的新媒体人，并且将比 Markdown Here 的公众号排版工作流节省2倍以上的，所以……放心上手。

在《如何在微信公众号实现一键排版》的文章中，我曾经介绍了如何使用 Markdown + Markdown Here 实现微信公众号文章一键排版的过程：

1.  在任意支持 Markdown 语法的工具上写好文章，比如简书、Typora等编辑器；
<img class="alignnone size-full wp-image-849" src="http://www.xgclass.cn/wp-content/uploads/2018/11/006tNc79gy1fp2286qanag30p00fn79j-2.gif" width="900" height="563" alt="" />

2.  然后将 Markdown 格式的文章内容复制出来；
<img class="alignnone size-full wp-image-850" src="http://www.xgclass.cn/wp-content/uploads/2018/11/006tNc79gy1fp228pco70g30p00fnn68-2.gif" width="900" height="563" alt="" />

3.  将复制的内容黏贴到微信公众号后台；
<img class="alignnone size-full wp-image-851" src="http://www.xgclass.cn/wp-content/uploads/2018/11/006tNc79gy1fp228r4vs7g30p00fnq8u-2.gif" width="900" height="563" alt="" />

4.  点击浏览器中的 Markdown Here 插件，渲染文章为自定义的格式；
<img class="alignnone size-full wp-image-852" src="http://www.xgclass.cn/wp-content/uploads/2018/11/006tNc79gy1fp229ecpahg30p00fn45h-2.gif" width="900" height="563" alt="" />

但是这个过程有2个重要的问题：

1.  **项目列表渲染会出错**：如果文章包括了项目列表的格式，点击 Markdown Here 的按钮渲染完成并保存后，这些项目列表的自定义格式就会丢失。虽然已经向微信公众号开发者社区提交了问题，但是始终都没有获得什么实质性的进展。
2.  **复制渲染的操作稍繁琐**：每一次写完都要复制 Markdown 源码到公众号后台，再点击渲染，其实也不是一个很高效率的过程。

于是我想：**既然我所有的写作都是在 Typora 完成的，如果写作的时候，Markdown 渲染的工作就同步在 Typora 完成了，那么不是可以避免在公众号后台出现的项目列表的渲染错误，而且也不用每一次都手动点击渲染按钮**。

因此解决这个问题最重要的就是「**如何在 Typora 中自定义 Markdown 的渲染样式**」。很幸运的时候，Google 关键词一搜索，就找到了非常完成的官方文档。

<img class="alignnone size-full wp-image-853" src="http://www.xgclass.cn/wp-content/uploads/2018/11/006tNc79gy1fp226awedaj31kw18rk5r-2.jpg" width="1280" height="1006" alt="typora-custom-css" />

来来回回调试了近2个小时，终于产出了这一套用于微信公众号的文章渲染规范。

<img class="alignnone size-full wp-image-854" src="http://www.xgclass.cn/wp-content/uploads/2018/11/006tNc79gy1fp2268tazwj31kw1bnk0f-2.jpg" width="1280" height="1071" alt="wechatcss" />

> 本文也是用这一套样式渲染出来的，回复「**[Typora CSS][1]**」获取开源CSS代码。

好了，现在让我们来看一下整个强悍的写作和发布流程吧！

1.  切换至使用 Typora 自定义样式，开始使用 Markdown 进行写作；
<img class="alignnone size-full wp-image-855" src="http://www.xgclass.cn/wp-content/uploads/2018/11/006tNc79gy1fp23ihzcrhj31kw17z7sx-1.jpg" width="1280" height="989" alt="06982ED6-B4C1-49B1-BA33-ADD096433C78" />

2.  写完以后，全选复制所有文章内容；
<img class="alignnone size-full wp-image-856" src="http://www.xgclass.cn/wp-content/uploads/2018/11/006tNc79gy1fp23jdj1mej31kw14rdlk-1.jpg" width="1280" height="916" alt="" />

3.  全选复制文章到微信公众号后台，保存发布！
<img class="alignnone size-full wp-image-857" src="http://www.xgclass.cn/wp-content/uploads/2018/11/006tNc79gy1fp23xv8twrj31kw10t79p-1.jpg" width="1280" height="828" alt="" />

排版的过程全程只需不到0.1秒的时间，投入2个小时做这件事情的性价比，嗯，我个人觉得还算满意。



[1]: https://github.com/BPteach/CM310-Exercise-Files/blob/master/%E7%AC%AC5%E7%AB%A0/TyporaWechat.css
