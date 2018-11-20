---
ID: 531
post_title: >
  微信公众号 Markdown Here
  渲染图片无法保存的解决办法
post_name: >
  solution-for-markdown-here-image-for-wechat
author: banpie
post_date: 2017-12-20 00:00:00
layout: post
link: >
  http://www.xgclass.cn/solution-for-markdown-here-image-for-wechat/
published: true
tags:
  - markdown
  - markdown here
  - 公众号
categories:
  - 工具1
---
因为微信公众号编辑器的限制的，当我们直接在后台使用 Markdown 语法渲染图片的时候，图片可以暂时显示，但是保存后图片就会丢失，这是因为微信编辑器不会自动把外链图片保存并上传到公众号后台导致的，这样一来，每一次渲染完后，都要手动重新插入图片，非常的麻烦。

那么有什么解决办法呢？方法有两个：

1.  **单平台发布的解决办法**：如果你只需要发布在公众号，方法很简单：渲染后全选文章，使用快捷键剪切，然后使用快捷键黏贴进去，图片便会自动上传到公众号后台了（感谢 @Comi 网友推荐）。
2.  **多平台发布的解决办法**：如果你需要同步发布多个平台，你可以通过 “[新榜编辑器][1] ”可以非常完美的解决这个问题，它的原理是：新榜编辑器可完美渲染 Markdown 文本，和微信公众号绑定后，便可以无缝的把渲染完的内容同步到微信公众号的后台。

第一种方法比较简单，所以本文介绍后面方法的具体实现步骤：

### 1\. 注册新榜编辑器账号

首先访问新榜编辑器网站，注册账号后填写对应信息登陆。

<img class="alignnone size-full wp-image-572" src="http://www.xgclass.cn/wp-content/uploads/2018/11/33872591.jpg" width="1280" height="662" alt="" />

### 2\. 绑定微信公众号

点击右上角的`授权管理`，绑定公众号。

<img class="alignnone size-full wp-image-573" src="http://www.xgclass.cn/wp-content/uploads/2018/11/9415306.jpg" width="1280" height="673" alt="" />

### 3\. 在新榜编辑器创建并渲染文章

使用 Markdown 语言撰写文章，并配合Markdown Here 渲染，填写对应的作者、标题、图片后，点击`保存文章`。

<img class="alignnone size-full wp-image-574" src="http://www.xgclass.cn/wp-content/uploads/2018/11/76517349.jpg" width="1280" height="659" alt="" />

### 4\. 同步文章

文章保存后，会出现在新榜编辑器的`我的内容`选项中，进入该选项卡后，点击文章下面的`一键同步到平台`，然后选择选择对应的平台同步即可。

<img class="alignnone size-full wp-image-575" src="http://www.xgclass.cn/wp-content/uploads/2018/11/85653617.jpg" width="1280" height="322" alt="" />

<img class="alignnone size-full wp-image-576" src="http://www.xgclass.cn/wp-content/uploads/2018/11/55662905.jpg" width="1280" height="607" alt="" />

### 5\. 发布微信公众号文章

同步后，文章就会出现在微信公众号后台的素材库中，你可以根据自己的需要进行群发。

<img class="alignnone size-full wp-image-577" src="http://www.xgclass.cn/wp-content/uploads/2018/11/19207262.jpg" width="1280" height="621" alt="" />

#

 [1]: https://edit.newrank.cn/