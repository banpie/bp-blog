---
post_title: 比 Markdown Here 更惊人的微信公众号发布指南出炉
post_date: 2017-12-20
post_name: solution-for-markdown-here-image-for-wechat
categories: 工具
published: true
typora-copy-images-to: ipic
---

> 本文适用任何水平、在任何平台写作的新媒体人，并且将比 Markdown Here 的公众号排版工作流节省2倍以上的，所以……放心上手。

在《如何在微信公众号实现一键排版》的文章中，我曾经介绍了如何使用 Markdown + Markdown Here 实现微信公众号文章一键排版的过程：

1. 在任意支持 Markdown 语法的工具上写好文章，比如简书、Typora等编辑器；

![](https://ws3.sinaimg.cn/large/006tNc79gy1fp2286qanag30p00fn79j.gif)

2. 然后将 Markdown 格式的文章内容复制出来；

![](https://ws3.sinaimg.cn/large/006tNc79gy1fp228pco70g30p00fnn68.gif)

3. 将复制的内容黏贴到微信公众号后台；

![](https://ws4.sinaimg.cn/large/006tNc79gy1fp228r4vs7g30p00fnq8u.gif)

4. 点击浏览器中的 Markdown Here 插件，渲染文章为自定义的格式；

![](https://ws3.sinaimg.cn/large/006tNc79gy1fp229ecpahg30p00fn45h.gif)

但是这个过程有2个重要的问题：

1. **项目列表渲染会出错**：如果文章包括了项目列表的格式，点击 Markdown Here 的按钮渲染完成并保存后，这些项目列表的自定义格式就会丢失。虽然已经向微信公众号开发者社区提交了问题，但是始终都没有获得什么实质性的进展。
2. **复制渲染的操作稍繁琐**：每一次写完都要复制 Markdown 源码到公众号后台，再点击渲染，其实也不是一个很高效率的过程。

于是我想：**既然我所有的写作都是在 Typora 完成的，如果写作的时候，Markdown 渲染的工作就同步在 Typora 完成了，那么不是可以避免在公众号后台出现的项目列表的渲染错误，而且也不用每一次都手动点击渲染按钮**。

因此解决这个问题最重要的就是「**如何在 Typora 中自定义 Markdown 的渲染样式**」。很幸运的时候，Google 关键词一搜索，就找到了非常完成的官方文档。

![typora-custom-css](https://ws1.sinaimg.cn/large/006tNc79gy1fp226awedaj31kw18rk5r.jpg)

来来回回调试了近2个小时，终于产出了这一套用于微信公众号的文章渲染规范。

![wechatcss](https://ws2.sinaimg.cn/large/006tNc79gy1fp2268tazwj31kw1bnk0f.jpg)

> 本文也是用这一套样式渲染出来的，回复「**[Typora CSS](https://github.com/BPteach/CM310-Exercise-Files/blob/master/%E7%AC%AC5%E7%AB%A0/TyporaWechat.css)**」获取开源CSS代码。 

好了，现在让我们来看一下整个强悍的写作和发布流程吧！

1. 切换至使用 Typora 自定义样式，开始使用 Markdown 进行写作；

![06982ED6-B4C1-49B1-BA33-ADD096433C78](https://ws3.sinaimg.cn/large/006tNc79gy1fp23ihzcrhj31kw17z7sx.jpg)

2. 写完以后，全选复制所有文章内容；

![](https://ws3.sinaimg.cn/large/006tNc79gy1fp23jdj1mej31kw14rdlk.jpg)

3. 全选复制文章到微信公众号后台，保存发布！

![](https://ws3.sinaimg.cn/large/006tNc79gy1fp23xv8twrj31kw10t79p.jpg)

排版的过程全程只需不到0.1秒的时间，投入2个小时做这件事情的性价比，嗯，我个人觉得还算满意。

> 如果你想要自定义标题，正文、强调文本等等样式，你可以阅读原文查看《[微信公众号终极排版指南](https://learn.bpteach.com/course/24?utm_source= wechat.qq.com&utm_medium=referral&utm_campaign=cm310-bp&utm_term=typora-css&utm_content=textlink)》。