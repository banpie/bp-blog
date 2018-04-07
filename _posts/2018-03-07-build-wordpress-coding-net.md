---
post_title: 纯技术小白如何利用Coding Pages搭建免费WordPress站点
post_date: 2018-03-07
post_name: build-wordpress-coding-net
categories: 职场
published: true
tag: [职场]
typora-copy-images-to: ipic
---

著名的学习大神 Scott Young ，他曾提到一个细节：在学习一个东西的时候，你能否用比喻的方式向一个 10 岁的小孩解释清楚？

号称终极快速学习法的「费曼技巧」强调：在你学习某个概念的过程中，如果你可以清楚地和别人解释这个概念，那么你才算是对很好地掌握了这个概念。

中国古话讲「教学相长」，古罗马著名斯多亚学派哲学家塞内加说过：「While we teach， We learn」，其实说的都是：**输出对于学习的重要性**。

对于通过「输出来倒逼学习」这一件事情，在现在的新媒体环境中并不是一件什么难事：我们有简书、有知乎专栏、有微信公众号等等。

但是如果长期写作下来，你会发觉有一个明显的问题：**毕竟是别人的平台，受限太多**。

比如，当你在想：

- 能不能把文章页修改成自己的域名？
- 能不能用户在订阅号输入关键词，自动放回文章的搜索结果？
- 能不能在文章的最后，推送自己写过的相关文章呢？
- …… 

而这些都需要依赖一个更强有力的内容管理系统（CMS）。

而说到强大的 CMS 系统，WordPress 应该是大多数人的选择。根据2017年USMS的报告，地球上近30%的网站使用WordPress 来搭建，大家所熟知的科技博客「TechCrunsh」，美国的「New York Times」纽约时报，国内的「人人都是产品经理」等等都是使用WordPress 搭建的。

WordPress 是什么呢？**简单的来说，它就是一个程序**。好像我们电脑上安装QQ程序来聊天，安装 Typora 程序来写作，而我们安装 WordPress 来管理内容。只是不太一样的是，WordPress 程序不是安装在普通的个人电脑上，而是需要安装在服务器电脑上才能运行。

![ACDB39A5-14B9-4BEC-9DC4-C2538CAE6ECE](https://ws3.sinaimg.cn/large/006tNc79ly1fp4g1371m0j31kw0xzqcl.jpg)

当然 WordPress 到今天其实已经不仅仅是用于做内容管理了，你还可以拿它来开网店、做论坛、做问答社区、搭建企业站点等等（半撇私塾的站点也是使用WordPress 搭建的）。

但是问题是，很多零基础学习 WordPress 的时候，常常听到「服务器」就打了退堂鼓。的确，**对于没有任何技术基础的人来说，一开始需要熟悉 FTP、域名、DNS 等等术语的过程是需要花费许多时间**。

那么，有没有什么办法可以帮助小白，**在不涉及任何服务器的情况下，利用现有的免费服务，搭建出一个强大的 WordPress 内容站点呢**？

Coding Pages！所以本文分享的就是利用 Coding Pages 实现 WordPress 动态网页托管的全过程。Coding Pages 是 Coding.net 推出的一项免费动态网页托管和演示服务，支持使用 PHP 语言和 MySQL 数据库，可用于部署开源博客、CMS 等动态应用。

接下来我们直接来看看整个实现的过程。

## 准备工作

在使用该服务之前，你需要做2件事情：

1. 注册 Coding.net 的账号；

![8BE22921-AC31-4D05-AE27-DC8102A97708](https://ws4.sinaimg.cn/large/006tNc79gy1fp4g3vjd75j31kw0vlafm.jpg)

2. 完善你的个人信息，将账号免费升级至「银牌会员」。

![8DC3F525-C838-40C0-AE70-168B97A0C586](https://ws3.sinaimg.cn/large/006tNc79ly1fp4g37mbb5j31i60swtfh.jpg)



## WordPress 搭建操作过程

下面是一个基于 WordPress 搭建「动态 Pages」的操作示例，示例 Pages 地址你可以查看：https://bpteach.cn/2G3Zlbi。

1. 在 https://bpteach.cn/2D4Brtn 页面右上角点击「Fork」将该项目复制到你自己的仓库。

![172FE42B-244C-47E4-820B-1369B694A1CF](https://ws2.sinaimg.cn/large/006tNc79gy1fp4g999p75j31kw0y949y.jpg)

2. 「Fork」完毕后，你自己的仓库就会出现名为「dpages-WordPress-Demo」的项目了。你需要在这个项目里点击「代码 -> Pages 服务」，选择「动态 Pages」 选项卡，点击「开启」，选择部署来源，点击「保存」。稍等片刻即可完成部署并通过 `xx.coding.io` 访问你的网站。

[![图片](https://dn-coding-net-production-pp.qbox.me/b4685f14-9ebb-4ed6-a1cc-0458e31fc7c6.png)](https://dn-coding-net-production-pp.qbox.me/b4685f14-9ebb-4ed6-a1cc-0458e31fc7c6.png)
[![图片](https://dn-coding-net-production-pp.qbox.me/d6b0f693-e612-491e-889e-89ac5dd0d081.png)](https://dn-coding-net-production-pp.qbox.me/d6b0f693-e612-491e-889e-89ac5dd0d081.png)

3. 同时，你需要在这个页面中点击存储空间栏中的「连接信息」获取数据库连接信息。

[![图片](https://dn-coding-net-production-pp.qbox.me/2e76fde7-f5ae-478f-944f-721072e0cc54.png)](https://dn-coding-net-production-pp.qbox.me/2e76fde7-f5ae-478f-944f-721072e0cc54.png)

4. 打开部署的网站，填入第 3 步中获取的信息。

[![图片](https://dn-coding-net-production-pp.qbox.me/6aa000f3-e64b-4166-8348-309e9f098ae5.png)](https://dn-coding-net-production-pp.qbox.me/6aa000f3-e64b-4166-8348-309e9f098ae5.png)

5、填写基本信息，安装 WordPress。

[![图片](https://dn-coding-net-production-pp.qbox.me/04df3395-1129-4369-8ab2-4b62f19c1939.png)](https://dn-coding-net-production-pp.qbox.me/04df3395-1129-4369-8ab2-4b62f19c1939.png)

6、安装完成后，你的网站就搭建成功了！（示例网站地址: ：https://bpteach.cn/2G3Zlbi）

![00CAF769-E2B7-4D9C-833F-983D440833A5](https://ws2.sinaimg.cn/large/006tNc79gy1fp4gscoh06j31kw0uf4aw.jpg)

7. 使用第 5 步中的信息登录 WordPress 后即可进入管理后台。

[![图片](https://dn-coding-net-production-pp.qbox.me/310a7de6-d9e7-4c36-84cd-6c500f10bd2d.png)](https://dn-coding-net-production-pp.qbox.me/310a7de6-d9e7-4c36-84cd-6c500f10bd2d.png)

当然，接下来你还可以做很多事情，比如：

- 你可以在 Coding.net 中绑定你自己的购买的域名；
- 你可以安装 Writing  on Github 来绑定你的 Github 仓库，实现自动同步；
- 你还可以安装微信机器人来实现用户在公众号输入关键词，自动返回文章
- …… 。

总之，WordPress 的折腾空间是无限之大的。后台插件的丰富、社区支持的完善，可以说到现在，几乎可以实现我平常工作中 95% 以上的内容管理需求。

WordPress 的开始，也是折腾的开始，祝你愉快。