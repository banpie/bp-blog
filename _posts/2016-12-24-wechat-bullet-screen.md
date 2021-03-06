---
ID: 475
post_title: >
  如何快速实现公众号文章弹幕效果
post_name: wechat-bullet-screen
author: 半撇banpie
post_date: 2016-12-24 00:00:00
layout: post
link: >
  https://www.banpie.info/wechat-bullet-screen/
published: true
tags:
  - 弹幕
  - 微信公众号
  - 新媒体自习室
categories:
  - 新媒体自习室
---
> “弹幕”起源于日本,网友们在观看视频时发出的评论以飞行的形式横穿屏幕,当出现很多评论时,就会产生如同无数子弹横飞的效果,这种现象被称作“弹幕”。弹幕的使用人群多为90后、00后,最先是在动画、漫画、游戏视频网站流行起来,如今已不仅限于视频，许多公众号也在文章中也做成这种互动弹幕的形式。来增强内容的呈现形式。

微信公众号中添加弹幕效果的方法也有很多种，比如可以利用PPT动画+Gif截图的方式直接生成对应的弹幕动态图来模拟，但是在本文中，我将分享的是如何利用现有的免费排版工具，修改一些基础的代码来实现自定义的弹幕效果。

## 实现公众号弹幕效果准备工作

在公众号中实现弹幕效果需要准备一下几项： - 任何支持富文本编辑的HTML编辑器（i排版／UE编辑器等等）； - 弹幕效果对应的文字效果（出现时长、字体类型、颜色）； - 弹幕所需要的文字组合；

## 实现公众号弹幕效果的基本步骤

1.  打开[i排版][1]网站；
2.  点击`弹幕`选项卡；
3.  选择第二项`文字弹幕`的样式；
4.  调节对应的文字后，复制到微信公众号后台；

## 弹幕效果的参数说明

具体关于各参数的说明如下：

    <text y="90" x="596" fill="rgb(223,34,28)" style="font-size:1.2em;box-sizing:border-box">
        新媒体自习室，每周五更新
        <animate attributename="x" from="800" to="-400" begin="1s" dur="10s" repeatcount="indefinite" style="box-sizing:border-box;"></animate>
    </text>
    

*   `text`的标签中，`y`和`x`表示弹幕文字的起始坐标点，`fil`l对应的是文字的颜色值，`font-size`对应的是文字的大小；
*   `animate`标签中，控制的是弹幕效果，`attributename`控制的是滚动方向，x表示水平方向，`from`和`to`就是从哪里滚动到哪里，然后`begin`是控制文字什么时间开始滚动，`dur`表示经过对应的时长后滚动到目的地；

增强内容呈现形式的方法还有很多，如果你也有好的案例和技巧，欢迎通过评论区告诉我。

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk2NTA4NTQ1OV19
-->

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQxMDE4NTM2Nl19
-->

 [1]: http://www.ipaiban.com/
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg4MjYwMzk4NF19
-->