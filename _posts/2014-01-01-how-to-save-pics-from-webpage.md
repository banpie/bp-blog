---
post_title: 网页图片不能保存怎么办？
post_name: how-to-save-pics-from-webpage
post_date: 2014-01-01 10:10:38
layout: post
published: true
tags:
  - Chrome
categories:
  - 工具
---
小玲平时做设计的时候经常要去网上找图片，可是有些网站很“抠门”将右键“图片另存为”的功能给屏蔽了，小玲这个捉急呀。最近经高人指点，小玲终于找到了解决这个问题的办法——利用Google Chrome审查元素保存网页图

Ps：只要有审查元素的浏览器都可以使用该方法，不限于Chrome。

## 第一步：右键——审查元素

比如：小玲想保存天猫中间“洗护月末采购”这张图片，先将鼠标放到要保存的图片上，点右键选择审查元素。

[![shenchayuansu_2](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/shenchayuansu_2.jpg)](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/shenchayuansu_2.jpg)

## 第二步：找到图片存储地址（URl）

*   点击审查元素后会弹出如下界面，我们可以看到title=”洗护月末疯狂购”证明这是我们要保存的这张图片的代码位置

*   在它上面找到有“background-image”的代码，点击一下选中，在右侧styles窗口中可以看到background-image的URI地址

*   将鼠标放到URL网址上右键——在新页面中打开（open link in new tab），这时我们打开了图片存储的地址。

[![shenchayuansu_3](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/shenchayuansu_3.jpg)](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/shenchayuansu_3.jpg)

## 第三步：图片另存为

打开图片后，将鼠标放到图片上右键——图片另存为，就将图片保存下来啦！

[![shenchayuansu_5](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/shenchayuansu_5.jpg)](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/shenchayuansu_5.jpg)

## 升级篇：查看网页所有图片

点击审查元素，如下图：选择Resources-Frames-Images，我们就可以看到网页的所有图片，选择你想要的图片存储吧。

[![shenchayuansu_4](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/shenchayuansu_4.jpg)](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/shenchayuansu_4.jpg)