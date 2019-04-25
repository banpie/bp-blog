---
ID: 419
post_title: >
  如何翻墙：使用Shadowsock搭建一条自由的梯子
post_name: shadowsocks-pac-gfw
author: 半撇
post_date: 2018-03-20 00:00:00
layout: post
link: >
  http://www.banpie.info/shadowsocks-pac-gfw/
published: true
tags: [ ]
categories:
  - 神器
  - 工具
  - 效率
---
在国内使用 Google 并不是一件非常容易的事情，虽然说目前还有部分的VPN，比如蓝灯，我们可以比较顺利地进行科学上网，打开新世界的大门，但是商用的VPN总会出现各种问题。

1.  **速度慢**：大部分提供VPN服务的公司通常是买了很多台国外的服务器，然后让几个用户一起共享其中的某一台服务器。
2.  **不稳定**：传统的VPN常常好几个人一起共享1台服务器，那么多人的时候就容易卡，就在在爬楼梯的过程中，太多人往1个方向跑，自然就会拥堵。遇到特殊时期管控严格的时候，一旦使用人数多了，容易被有关部分发现：这个地方的人流怎么这么多？这样以来很容易进行IP封锁，这也就意味着VPN也废了。

那么有什么什么一劳永逸的办法来避免这个问题呢？当然是有的，这个方法我称之为“自建梯子”：自己买1台国外的服务器，自己在上面安装 VPN，自己享受这条梯子！

虽然对于小白来说，“买服务器”可能听起来已经比较复杂，更不用说使用命令行安装服务器软件了，但是其实这一切的工作都可以通过点击鼠标来完成。接下来，我们就介绍如何利用"搬瓦工"这一家 VPS 服务器提供商来自建梯子。

## 一、搬瓦工是什么？

搬瓦工是一家著名的低价 VPS 提供商（英文全称：BandwagonHost），早先曾经推出过年付 3 美元的VPS（虚拟专用服务器），当然这已成为历史。目前在售的 VPS 月付不过 3 美元，年付不过 20 美元，年付平均到每月仅 10 元人民币多一点，比购买现成的 VPN 便宜很多。

选择搬瓦工主要的优势在于：

1.  价格低廉，服务可靠稳定。
2.  后台提供一键 ShadowSocks 功能，傻瓜操作。
3.  支持支付宝付款，无须信用卡。
4.  支持退款。

## 二、Shadowsocks 是什么？

在很久很久以前，我们访问各种网站都是简单而直接的，用户的请求通过互联网发送到服务提供方，服务提供方直接将信息反馈给用户。

[<img class="alignnone size-full wp-image-2575" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-42.png" width="591" height="122" alt="ss-01" />][1]

然后有一天，[GFW][2] 就出现了，他像一个收过路费的强盗一样夹在了在用户和服务之间，每当用户需要获取信息，都经过了 GFW，GFW将它不喜欢的内容统统过滤掉，于是客户当触发 GFW 的过滤规则的时候，就会收到`Connection Reset`这样的响应内容，而无法接收到正常的内容。

[<img class="alignnone size-full wp-image-2576" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-43.png" width="600" height="129" alt="ss-02" />][3]

聪明的人们想到了利用境外服务器代理的方法来绕过 GFW 的过滤，其中包含了各种HTTP代理服务、Socks服务、VPN服务… 其中以 ssh tunnel 的方法比较有代表性。

*   1).首先用户和境外服务器基于 ssh 建立起一条加密的通道；
*   2-3) 用户通过建立起的隧道进行代理，通过 ssh server 向真实的服务发起请求；
*   4-5) 服务通过 ssh server，再通过创建好的隧道返回给用户；

[<img class="alignnone size-full wp-image-2578" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-45.png" width="723" height="133" alt="ss-03" />][4]

由于 ssh 本身就是基于 RSA 加密技术，所以 GFW 无法从数据传输的过程中的加密数据内容进行关键词分析，避免了被重置链接的问题，但由于创建隧道和数据传输的过程中，ssh 本身的特征是明显的，所以 GFW 一度通过分析连接的特征进行干扰，导致 ssh 存在被定向进行干扰的问题。

于是有人想了一个办法，就是在你的电脑和服务器上都同是安装shadowsocks ，因为本地的 Shadowsocks 客户端一般是本机或路由器或局域网的其他机器，不经过 GFW，所以解决了上面被 GFW 通过特征分析进行干扰的问题（[点击了解更多原理][5]）。

[<img class="alignnone size-full wp-image-2579" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-46.png" width="692" height="321" alt="ss-04" />][6]

更简单地说，就是需要你同时在你购买的服务器和你的电脑上安装 Shadowsocks 软件，下面我们将从vps购买开始，直到搭建成功ShadowSocks，对搬瓦工 VPS 搭建 Shadowsocks VPN 进行一个完整的介绍。

## 三、利用Shadowsocks + 搬瓦工 VPS 自建梯子的步骤

核心的步骤就是四步：

1.  购买VPS服务器；
2.  在VPS服务器上安装Shadowsocs；
3.  在本地电脑上安装Shadowsocks；
4.  开启翻墙模式！

### **3\.1 购买VPS**

首先我们需要访问 [搬瓦工][7] （如访问缓慢，请使用 *[bwh88.net][8]* 访问）购买VPS（如果你无法访问这个网站，有可能是被墙了，所以先使用类似的蓝灯VPN 切换到全局模式下访问后再购买），对于个人使用而言（每个月500G流量），可以选最便宜的每月2.99$，折合人民币也就20块几毛，和市面大部分收费的 VPN 费用差不多。

[<img class="alignnone size-full wp-image-2581" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-10.jpeg" width="1240" height="632" alt="image1" />][9]

选择KVM， 因为据说KVM是完全虚拟的，可以说是最真实的虚拟机，内存不共享，并且可以做很多事情，比如装docker，但是你选择OVZ 也可以。

[<img class="alignnone size-full wp-image-2584" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-166.jpg" width="1240" height="686" alt="image" />][10]

有按月按季度按年的，先选个按月的，第一次用也不知道稳不稳定。Location是服务器的地址，到时候打开谷歌首页显示的国家会和这个相关。

[<img class="alignnone size-full wp-image-2587" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-11.jpeg" width="1240" height="726" alt="" />][11]

确认之后点击点击 **Checkout**

[<img class="alignnone size-full wp-image-2589" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-170.jpg" width="1240" height="669" alt="image" />][12]

填写完相关的资料后付款，选择Alipay直接支付宝扫码付款。：）

[<img class="alignnone size-full wp-image-2591" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-12.jpeg" width="1240" height="636" alt="image" />][13]

### **3\.2 安装Shadowsocks服务器**

安装Shadowsocks服务器分为3种情况：

*   *   **自带安装法**：老版的服务器通常自带了Shadowsocks入口，你只需要点击一个按钮安装就可以，具体查看下方教程。
*   *   **隐藏安装法**：部分服务器可以通过特定的URL访问Shadowsocks入口，然后再点击按钮直接安装，具体查看下方教程。
*   *   **SSH安装法**：上面两个方法都没有的，可以借助快捷脚本安装，具体查看下方教程。

#### 3\.2.1 自带安装法

购买成功后回到首页，先选择右上角的 **Client Area**，然后选择 **My Services**

[<img class="alignnone size-full wp-image-2594" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-13.jpeg" width="1240" height="673" alt="image1" />][14]

点击 **KiwiVM Control Panel** 进入服务器的控制面板

[<img class="alignnone size-full wp-image-2596" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-14.jpeg" width="1240" height="681" alt="image1" />][15]

侧边栏选择 **Main controls**，可以看到当前服务器的信息，**IP**地址后续需要提供给客户端。操作系统默认安装了 **Centos**，你可以在左边的 **Install new OS** 中选择其他的系统，有**Ubuntu**和**Debian**，只需几分钟便可重装完毕。

不过最好还是使用 **Centos**，因为系统提供一键安装Shadowsocks的脚本只支持 **Centos**，换了其他系统的话脚本安装会失败，除非你会在对应系统上自己手动安装。

[<img class="alignnone size-full wp-image-2599" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-15.jpeg" width="1240" height="657" alt="image1" />][16]

点击侧边栏最下方的 **Shadowsocks Server** 选项，进入之后直接点击 **Install Shadowsocks Server** 按钮，运行脚本在服务器上安装Shadowsocks，稍等片刻安装完毕。

[<img class="alignnone size-full wp-image-2602" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-48.png" width="1240" height="759" alt="image1" />][17]

安装完成后重新点击 **Shadowsocks Server** 选项，进入界面后便可看到 **Shadowsocks server** 的相关信息，主要有**加密方式**，**端口号**，**服务器密码**，后续客户端连接服务器需要用到这些信息。

[<img class="alignnone size-full wp-image-2611" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-16.jpeg" width="1240" height="668" alt="image1" />][18]

#### 3\.2.2 隐藏安装法

由于目前搬瓦工已经隐藏了 Shadowsocks 的安装入口，不过针对部分的服务器，它的这功能没被删除，只是隐藏而已（前提：Shadowsocks 隐藏入口需要系统选择 Centos6 可以选带BBR的）

具体的步骤为：

1.  **登陆搬瓦工**：[搬瓦工地址][8]。
2.  **进入KiwiVM 后台**：找到购买的主机，点击“[KiwiVM Control Panel][19]”。
3.  **安装 Shadowsocks**：访问`https://kiwivm.64clouds.com/preloader.php?load=/main-exec.php?mode=extras_shadowsocks`，然后点击`Install Shadowsocks Server`完成安装。 <img class="alignnone size-full wp-image-1556" src="//www.banpie.info/wp-content/uploads/2019/02/2019-02-14-023714.png" width="1054" height="285" alt="" />
4.  **查看Shadowsocks信息**：点击`Go back`返回之前的页面(`[https://kiwivm.64clouds.com/main-exec.php?mode=extras_shadowsocks`，可以看到相关的账号信息和使用方法。 <img class="alignnone size-full wp-image-1557" src="//www.banpie.info/wp-content/uploads/2019/02/2019-02-14-023725.png" width="1062" height="674" alt="img" />
5.  完成！

#### 3\.2.3 SSH安装法

具体可参考[一键脚本搭建ss][20]。

### 3\.3 安装Shadowsocks客户端

**Shadowsocks**客户端的 [下载地址][74] ，可以看到有各种客户端的下载。貌似这货也是得翻墙才能访问到。

[<img class="alignnone size-full wp-image-2615" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-188.jpg" width="1240" height="705" alt="image" />][21]

#### **3\.3.1 Mac配置**

用的是Mac电脑，所以点击相关链接。东西都挂在github上，下载对应的zip文件，下载完成后安装并运行起来。

[<img class="alignnone size-full wp-image-2618" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-17.jpeg" width="1240" height="710" alt="image1" />][22]

点击图标，进入 **服务器设置**

[<img class="alignnone size-full wp-image-2622" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-18.jpeg" width="1240" height="896" alt="image1" />][23]

主要有四个地方要填，**服务器的地址**，**端口号**，**加密方法**，**密码**。服务器地址即为之前 **Main controls**选项中的IP地址。端口号、加密方法、密码必须与之前 **Shadowsocks Server** 中的信息一一匹配，否则会连接失败。

[<img class="alignnone size-full wp-image-2626" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-19.jpeg" width="1240" height="1109" alt="image1" />][24]

设置完成后点击确定，然后服务器选择这个配置，默认选中PAC自动模式，确保Shadowsocks状态为**On**，这时候打开谷歌试试~

[<img class="alignnone size-full wp-image-2630" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-20.jpeg" width="1240" height="609" alt="image1" />][25]

Google图标右下角显示的是Canada，因为之前服务器的地址选的是加拿大：）

#### **3\.3.2 iOS配置**

iOS上用的VPN App 是**Wingy**，可以App Store上直接搜。官方的**Wingy**下载是免费的，注意分辨有些图标相似的App。

下载完成后运行，点击 **选择线路**

[<img class="alignnone size-full wp-image-2632" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-21.jpeg" width="719" height="1280" alt="image1" />][26]

选择 **新增线路**

[<img class="alignnone size-full wp-image-2635" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-22.jpeg" width="721" height="1280" alt="image1" />][27]

选择 **Shadowsocks(R)**

[<img class="alignnone size-full wp-image-2638" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-23.jpeg" width="727" height="1280" alt="image1" />][28]

在配置界面填写服务器相关的信息，和Mac上的一样，填写完成后保存，然后在首页进行连接。

[<img class="alignnone size-full wp-image-2641" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-24.jpeg" width="722" height="1280" alt="image1" />][29]

这样一来手机也能愉快的翻墙了。当然其他端的配置方式也基本一致，可以根据使用的平台下载对应的客户端。下载好的客户端最后自己在别处备份一下，因为官网需要翻墙，以方便后续其他未翻墙的机器下载。

最后，自己搭建的 VPN 好处是可以和别人共享，告诉别人相关的配置信息即可。市面上一些收费的 VPN 还会有限制，比如说不让看 YouTube 有一定流量限制不能分享账号否则封号等。

[1]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-42.png
[2]: http://zh.wikipedia.org/wiki/%E9%87%91%E7%9B%BE%E5%B7%A5%E7%A8%8B
[3]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-43.png
[4]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-45.png
[5]: https://vc2tea.com/whats-shadowsocks/
[6]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-46.png
[7]: https://bandwagonhost.com/aff.php?aff=11742
[8]: http://bwh88.net/aff.php?aff=11742
[9]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-10.jpeg
[10]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-166.jpg
[11]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-11.jpeg
[12]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-170.jpg
[13]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-12.jpeg
[14]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-13.jpeg
[15]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-14.jpeg
[16]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-15.jpeg
[17]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-48.png
[18]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-16.jpeg
[19]: https://www.wervps.com/goto/nhk3t9g
[20]: https://flyzyblog.com/install-ss-ssr-bbr-in-one-command/
[21]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-188.jpg
[22]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-17.jpeg
[23]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-18.jpeg
[24]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-19.jpeg
[25]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-20.jpeg
[26]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-21.jpeg
[27]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-22.jpeg
[28]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-23.jpeg
[29]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-24.jpeg