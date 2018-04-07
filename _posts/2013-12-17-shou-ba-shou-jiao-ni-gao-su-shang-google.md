---

post_title: 如何利用修改Hosts文件高速使用Google服务
post_name: shou-ba-shou-jiao-ni-gao-su-shang-google

post_date: 2013-12-17 22:27:16
layout: post

published: true
tags: [ ]
categories:
  - 工具
---
2014.11.07更新：最新的Google 翻墙Hosts地址可以参见[鲁夫的博客](http://opengg.me/613/generate-hosts-for-google/)。

Google有太多牛x的产品了，Google Search, Gmail, Google+, Google Drive, Google Analytics……只可惜在我天朝之内，耗尽全部感情去访问一个Google搜索，却经常会被无情的返回一个“此页面不存在”的页面。

今天，阿半教你通过修改本地Hosts文件，几招就能顺利畅游Google（有一点遗憾是，如果需要访问Youtube视频，还是需要[利用Goagent进行科学上网的](http://www.banpie.info/how-to-use-goagent-to-science-online/ "如何利用Goagent进行科学上网")）

## 1、打开本地Hosts文件

Hosts这个神秘兮兮的文件其实就藏在你电脑的C盘里，按照这个路径打开：C:\Windows\System32\drivers\etc

![hosts](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/hosts.png)

## 2、复制网络Hosts列表

点击这份网络[Hosts列表](http://opengg.me/wp-content/uploads/2011/09/hosts.php)，按住键盘的“**Ctrl+A**”全选文本，然后再按住“**Ctrl+C**”复制Hosts文本。

[![smartladder.googlecode.com svn hosts pc hosts](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/smartladder.googlecode.com-svn-hosts-pc-hosts.png)](http://www.banpie.info/wp-content/uploads/2013/12/smartladder.googlecode.com-svn-hosts-pc-hosts.png)

## 3、粘贴并保存至本地Hosts文件

在这里，Windows 7/8系统的用户和Windows XP的用户的操作有点不同：

*   Windows XP的用户：对准Hosts文件**右击鼠标 **-&gt;选择弹出菜单中的“**打开方式**” -&gt; 选择“**记事本**”打开 -&gt; 在打开的记事本中按下键盘的“**Ctrl+V”**，将复制的网络Host是列表粘贴到此Hosts文档中 -&gt; 按住“**Ctrl+S**”保存即可

*   Windows 7/8的用户：将Hosts文件从etc的文化夹中**拖动到桌面 **-&gt; **重复**上面Windows XP用户的操作 -&gt; 按住“**Ctrl+S**”保存 -&gt; 把这个Hosts文档，再拖回原来的etc文件夹里；

![hosts paste](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2013/12/hosts-paste.png)

恭喜你，现在就可以高速畅游Google啦！你可以试一试这个[链接](https://mail.google.com)，看看你的Gmail打开是不是很快啊？