---
ID: 160
post_title: 如何锻造一个私人专属邮箱
post_name: how-to-create-a-bussiness-email
author: 半撇banpie
post_date: 2014-07-17 14:52:38
layout: post
link: >
  https://www.banpie.info/how-to-create-a-bussiness-email/
published: true
tags: [ ]
categories:
  - 工具
---
> @小小**晶：撇撇大人，你给我发的那种带@banpie.info后缀的邮箱是怎么弄啊？

你应该看过许多博客的联系邮箱多是：xxx@xxx.com，xxx@xxx.net，xxx@xxx.info吧？如此高贵冷艳的极客气质，半撇自然也未能逃过这场虚荣的“浩劫”。

[![banpie email signature][1]][1]

拥有一个带自己域名后缀的专属邮箱，除了B格较高之外，主要有几个好处：

*   **营销价值高**：邮箱地址的后缀就是官网域名，利用网站流量的导

*   **邮箱的绝对控制权**：因为对邮箱拥有绝对自主权，可以不用更换的邮箱地址的前提下，轻易地“搬家”（比如从腾讯搬家到搜狐

*   **更强的防垃圾邮件能力**：较普通私人邮箱，企业邮箱在防垃圾邮件能力上更强大为自己打造一个专属的企业邮箱，你只需要有：**一个独立的域名**。（如果没有，可以自己上淘宝或者万网购买一个）

接着呢？你只需在你的域名管理界面，**增加一条MX解析记录**就OK了。这条记录的作用在于：比如，当某人发送邮件到xxx@banpie.info的时候，我们的域名管理服务器就会把这份邮件，发送到半撇绑定的腾讯企业邮箱里。

具体步骤看下面，本课程也以**banpie.info域名**和**腾讯企业邮箱**为例子，当然，网易、腾讯、搜狐、新浪企业邮箱都可以，看个人选择，半撇推荐腾讯。

## 1、开通企业邮箱服务

访问[www.exmail.qq.com][2] -> 点击左上角的“**开通**” ->再点击页面下方中部的“**免费开通**”链接。

[![apply for qq Enterprise mailbox][3]][3]

## 2、注册企业邮箱

填写登陆企业邮箱的**登陆名**、**密码**、**密保邮箱**后，之后，你的密保邮箱会收到一份验证邮件。

[![register qq Enterprise mailbox][4]][4]

## 3、 添加企业域名

登陆密保邮箱激活账号后，你会跳转到域名添加页面，在www后面输入你购买的“**域名地址**”，例如：banpie.info，点击“**下一步**”。

[![domain input for qq enterprise mailbox][5]][5]

## 4、增加域名解析记录

登陆你的域名管理界面中（banpie.info使用的是DNSPod），点击“**添加记录**”，填写如下MX记录，保存即可。

*   邮件服务器名：mxbiz2.qq.com 优先级：1

*   邮件服务器名：mxbiz2.qq.com 优先级：10

[![dnspod for qq enterprise mailbox][6]][6]

## 5、添加成员邮箱

解析完成后，访问[www.exmail.qq.com][7]，使用第一步中的注册信息进行登陆，进入管理页面 -> 点击**“添加成员”** -> 输入新增成员的**姓名**、**邮箱账号**、**默认密码**等信息后，你就可以登陆访问该邮箱了，界面和你常用了QQ邮箱一模一样

[![add account in qq enterprise mailbox][8]](http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2014/07/add-account-in-qq-enterprise-mailbox.jpg

[![example of qq enterprise mailbox][9]][9]

## 6、更多

*   如果你想通过“mail.你的域名”访问你的邮箱管理页面，比如mail.banpie.info，你可以到域名管理界面增加一条CNAME记录，主机记录为：mail，记录值为：exmail.qq.com

*   如果你或者你想通过QQ面板的邮件按钮直接登陆企业邮箱，登陆企业邮箱后，点击“设置” ->“提醒服务”选项卡进行QQ号的绑定。

 [1]: http://www.banpie.info/wp-content/uploads/2018/11/banpie-email-signature.jpg
 [2]: http://exmail.qq.com/
 [3]: http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2014/07/apply-for-qq-Enterprise-mailbox.jpg
 [4]: http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2014/07/register-qq-Enterprise-mailbox.jpg
 [5]: http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2014/07/domain-input-for-qq-enterprise-mailbox.jpg
 [6]: http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2014/07/dnspod-for-qq-enterprise-mailbox.jpg
 [7]: http://www.exmail.qq.com/
 [8]: http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2014/07/add-account-in-qq-enterprise-mailbox.jpg
 [9]: http://7arnhx.com1.z0.glb.clouddn.com/wp-content/uploads/2014/07/example-of-qq-enterprise-mailbox.jpg
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NTA3MzYwNDVdfQ==
-->