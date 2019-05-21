---
ID: 155
post_title: 如何利用Goagent进行科学上网
post_name: how-to-use-goagent-to-science-online
author: 半撇banpie
post_date: 2014-06-24 12:37:12
layout: post
link: >
  https://www.banpie.info/how-to-use-goagent-to-science-online/
published: true
tags: [ ]
categories:
  - 未分类
---
你懂的，墙外风光无限美好

Updated 2014/06/25：

Goagent 如果出现大量的黄色错误，请搭配 GoGo Tester IP检测工具使用，将检测出的可用的Google IP复制替换至Goagent文件夹的Proxy.ini中。具体替换教程和软件下载见百度盘：http://pan.baidu.com/s/1jG40o1w （请勿慌张，即使完全不懂代码，只要一步一步操作，满速上Youtube都不是问题！）

最近 Google 被墙的厉害，我想是到了做翻墙教程的时候了。听月光博客说，Google 今天之后可能会慢慢的永久性告别……（内心默操无数次），请大家务必口口相传 Google 的一切产品。

在这片神奇的土地上，翻墙应该是每个网友必需掌握的技能，本教程介绍用 GAE（Google App Engine）翻墙的方法。GAE 的优点包括：免费、非常稳定、大流量，并且足够让你在 YouTube 上看各种高清视频了。

正值敏感时期，如果你上不去 Google，用这个免翻墙的地址可以正常访问：<https://s3-ap-southeast-1.amazonaws.com/google.cn/index.html>，或者暂且用微软的 Bing 搜索也还不错。

*   准备工作：本教程开始之前需要准备 Gmail 账号和 Chrome 浏览器

*   特别提醒：本教程给动手能力强的人，不需要懂什么技术，但是你要有耐心，因为过程有点微长。

## 1、登陆Google App Engine

打开：<http://appengine.google.com/>，输入Gmail用户密码登入。

[<img class="alignnone size-full wp-image-28201906" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-983/0-3.png" width="620" height="387" alt="" />][1]

## 2、创建应用

登录之后，自动转向「Application」注册页面，如下图，然后点击「Create Application」进入下一步。

[<img class="alignnone size-full wp-image-28211907" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-283/0-9-2.jpg" width="671" height="200" alt="" />][2]

## 3、手机号码验证

输入自己的手机号，注意前面需要+86（如：+8613888888888）。

[<img class="alignnone size-full wp-image-28221908" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2833/0-10-2.jpg" width="650" height="344" alt="" />][3]

## 4、验证成功

手机收到验证码后输入，验证成功后申请完成。

[<img class="alignnone size-full wp-image-28231909" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2843/0-11-2.jpg" width="624" height="256" alt="" />][4]

## 5、输入创建应用所需信息

转入「My Applications」页面后，点击「Create an Application」，新建应用创建一个app_id，比如：abc555，注意记下这个app_id，后面还会再用到。最后点击「Create Application」完成整个注册过程。

[<img class="alignnone size-full wp-image-28241910" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2853/0-12-2.jpg" width="767" height="540" alt="" />][5]

[<img class="alignnone size-full wp-image-28251911" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2863/0-13-2.jpg" width="684" height="361" alt="" />][6]

## 6、下载解压Goagent软件

访问https://code.google.com/p/goagent/ 下载goagent并解压，解压下载包后里面有 local 和 server 两个文件夹，后面步骤所提到的文件路径都在这两个文件夹里。

[<img class="alignnone size-full wp-image-28261912" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2873/0-14-2.jpg" width="718" height="310" alt="" />][7]

[<img class="alignnone size-full wp-image-28271913" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2883/0-15-2.jpg" width="634" height="178" alt="" />][8]

## 7、修改appid

用记事本打开并修改local文件夹中的proxy.ini文件，将 [gae] 下的appid修改为<你申请到的appid>，多个appid用|分开(用windows的记事本也可以）。

[<img class="alignnone size-full wp-image-28281914" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2893/0-16-3.jpg" width="555" height="566" alt="" />][9]

## 8、上传应用到服务端

双击打开server文件夹下的uploader.bat文件, 输入你的appid和Gmail帐号、密码，将应用上传到服务端，多个appid用|隔开，请无视黑框里最后的提示。

[<img class="alignnone size-full wp-image-28291915" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2903/0-17-1.jpg" width="674" height="440" alt="" />][10]

## 9、安装Chrome的代理插件

打开 Chrome 后，在地址栏输入chrome://extensions/，后按回车打开扩展管理页，将local文件夹中的 SwitchySharp.crx 拖拽到该页面之后点击确定即可安装，扩展也可以从Chrome应用商店获得搜索 Proxy Switchy Sharp 获得。

[<img class="alignnone size-full wp-image-28301916" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2913/0-18-2.jpg" width="900" height="453" alt="" />][11]

## 10、导入代理设置文件

右键点击 Chrome 地址栏右侧的的 Proxy SwitchySharp 图标 -> 选择「选项」 -> 「导入/导出」，点击「从文件中恢复」，浏览到Local文件夹中的SwitchyOptionsOptions.bak这个文件，点击「确定」导入设置。

[<img class="alignnone size-full wp-image-28311917" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-993/0-4.png" width="1067" height="589" alt="" />][12]

[<img class="alignnone size-full wp-image-28321918" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2923/0-19.jpg" width="900" height="526" alt="" />][13]

## 11、开启代理

单击 Chrome 地址栏右侧 Proxy SwitchySharp 图标，选择「自动切换模式」。

[<img class="alignnone size-full wp-image-28331919" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-2933/0-20.jpg" width="176" height="326" alt="" />][14]

## 12、开启Goagent代理软件

开启打开local文件夹下的 goagent.exe启动代理，此时，你已在墙外。

[<img class="alignnone size-full wp-image-28341920" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-1003/0-5.png" width="838" height="474" alt="" />][15]

 [1]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-98.png
 [2]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-282.jpg
 [3]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-283.jpg
 [4]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-284.jpg
 [5]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-285.jpg
 [6]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-286.jpg
 [7]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-287.jpg
 [8]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-288.jpg
 [9]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-289.jpg
 [10]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-290.jpg
 [11]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-291.jpg
 [12]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-99.png
 [13]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-292.jpg
 [14]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-293.jpg
 [15]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-100.png
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTE2NjkxNTU3XX0=
-->