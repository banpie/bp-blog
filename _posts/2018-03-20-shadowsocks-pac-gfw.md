---
post_title: 如何翻墙：使用Shadowsock搭建一条自由的梯子
post_date: 2018-03-20
post_name: shadowsocks-pac-gfw
published: true
---

在国内使用Google 并不是一件非常容易的事情，虽然说目前还有部分的VPN，比如蓝灯，我们可以比较顺利地进行科学上网，打开新世界的大门，但是商用的VPN总会出现各种问题。

1. **速度慢**：大部分提供VPN服务的公司通常是买了很多台国外的服务器，然后让几个用户一起共享其中的某一台服务器。
2. **不稳定**：传统的VPN常常好几个人一起共享1台服务器，那么多人的时候就容易卡，就在在爬楼梯的过程中，太多人往1个方向跑，自然就会拥堵。遇到特殊时期管控严格的时候，一旦使用人数多了，容易被有关部分发现：这个地方的人流怎么这么多？这样以来很容易进行IP封锁，这也就意味着VPN也废了。

那么有什么什么一劳永逸的办法来避免这个问题呢？当然是有的，这个方法我称之为“自建梯子”：自己买1台国外的服务器，自己在上面安装 VPN，自己享受这条梯子！

虽然对于小白来说，“买服务器”可能听起来已经比较复杂，更不用说使用命令行安装服务器软件了，但是其实这一切的工作都可以通过点击鼠标来完成。接下来，我们就介绍如何利用"搬瓦工"这一家 VPS 服务器提供商来自建梯子。

## 一、搬瓦工是什么？

搬瓦工是一家著名的低价 VPS 提供商（英文全称：BandwagonHost），早先曾经推出过年付 3 美元的VPS（虚拟专用服务器），当然这已成为历史。目前在售的 VPS 月付不过 3 美元，年付不过 20 美元，年付平均到每月仅 10 元人民币多一点，比购买现成的 VPN 便宜很多。

选择搬瓦工主要的优势在于：

1. 价格低廉，服务可靠稳定。
2. 后台提供一键 ShadowSocks 功能，傻瓜操作。
3. 支持支付宝付款，无须信用卡。
4. 支持退款。

## 二、Shadowsocks 是什么？

在很久很久以前，我们访问各种网站都是简单而直接的，用户的请求通过互联网发送到服务提供方，服务提供方直接将信息反馈给用户。

![ss-01](http://upload-images.jianshu.io/upload_images/1668324-686b630266d7979e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

然后有一天，[GFW](http://zh.wikipedia.org/wiki/%E9%87%91%E7%9B%BE%E5%B7%A5%E7%A8%8B) 就出现了，他像一个收过路费的强盗一样夹在了在用户和服务之间，每当用户需要获取信息，都经过了 GFW，GFW将它不喜欢的内容统统过滤掉，于是客户当触发 GFW 的过滤规则的时候，就会收到`Connection Reset`这样的响应内容，而无法接收到正常的内容。

![ss-02](http://upload-images.jianshu.io/upload_images/1668324-43d48a47cd5e37d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

聪明的人们想到了利用境外服务器代理的方法来绕过 GFW 的过滤，其中包含了各种HTTP代理服务、Socks服务、VPN服务… 其中以 ssh tunnel 的方法比较有代表性。

- 1).首先用户和境外服务器基于 ssh 建立起一条加密的通道；
- 2-3) 用户通过建立起的隧道进行代理，通过 ssh server 向真实的服务发起请求；
- 4-5) 服务通过 ssh server，再通过创建好的隧道返回给用户；

![ss-03](http://upload-images.jianshu.io/upload_images/1668324-79f777a9b7a84c7f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

由于 ssh 本身就是基于 RSA 加密技术，所以 GFW 无法从数据传输的过程中的加密数据内容进行关键词分析，避免了被重置链接的问题，但由于创建隧道和数据传输的过程中，ssh 本身的特征是明显的，所以 GFW 一度通过分析连接的特征进行干扰，导致 ssh 存在被定向进行干扰的问题。

于是有人想了一个办法，就是在你的电脑和服务器上都同是安装shadowsocks ，因为本地的 Shadowsocks 客户端一般是本机或路由器或局域网的其他机器，不经过 GFW，所以解决了上面被 GFW 通过特征分析进行干扰的问题（[点击了解更多原理](https://vc2tea.com/whats-shadowsocks/)）。

![ss-04](http://upload-images.jianshu.io/upload_images/1668324-52433ff789fc9d91.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

更简单地说，就是需要你同时在你购买的服务器和你的电脑上安装 Shadowsocks 软件，下面我们将从vps购买开始，直到搭建成功ShadowSocks，对搬瓦工 VPS 搭建 Shadowsocks VPN 进行一个完整的介绍。

## 三、利用Shadowsocks + 搬瓦工 VPS 自建梯子的步骤

核心的步骤就是四步：

1. 购买VPS服务器；
2. 在VPS服务器上安装Shadowsocs；
3. 在本地电脑上安装Shadowsocks；
4. 开启翻墙模式！

### **3.1 购买VPS**

首先我们需要访问 [搬瓦工](https://bandwagonhost.com/aff.php?aff=11742) （如访问缓慢，请使用 *bwh1.net* 访问）购买VPS（如果你无法访问这个网站，有可能是被墙了，所以先使用类似的蓝灯VPN 切换到全局模式下访问后再购买），对于个人使用而言（每个月500G流量），可以选最便宜的每月2.99$，折合人民币也就20块几毛，和市面大部分收费的 VPN 费用差不多。

![image1](https://moshuqi.github.io/images/posts/vpn/1.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

选择KVM， 因为据说KVM是完全虚拟的，可以说是最真实的虚拟机，内存不共享，并且可以做很多事情，比如装docker，但是你选择OVZ 也可以。

![image1](https://moshuqi.github.io/images/posts/vpn/2.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

有按月按季度按年的，先选个按月的，第一次用也不知道稳不稳定。Location是服务器的地址，到时候打开谷歌首页显示的国家会和这个相关。

![image1](https://moshuqi.github.io/images/posts/vpn/3.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

确认之后点击点击 **Checkout**

![image1](https://moshuqi.github.io/images/posts/vpn/4.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

填写完相关的资料后付款，选择Alipay直接支付宝扫码付款。：）

![image1](https://moshuqi.github.io/images/posts/vpn/5.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### **3.2 安装Shadowsocks服务器**

购买成功后回到首页，先选择右上角的 **Client Area**，然后选择 **My Services**

![image1](https://moshuqi.github.io/images/posts/vpn/6.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

点击 **KiwiVM Control Panel** 进入服务器的控制面板

![image1](https://moshuqi.github.io/images/posts/vpn/7.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

侧边栏选择 **Main controls**，可以看到当前服务器的信息，**IP**地址后续需要提供给客户端。操作系统默认安装了 **Centos**，你可以在左边的 **Install new OS** 中选择其他的系统，有**Ubuntu**和**Debian**，只需几分钟便可重装完毕。

不过最好还是使用 **Centos**，因为系统提供一键安装Shadowsocks的脚本只支持 **Centos**，换了其他系统的话脚本安装会失败，除非你会在对应系统上自己手动安装。

![image1](https://moshuqi.github.io/images/posts/vpn/8.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

点击侧边栏最下方的 **Shadowsocks Server** 选项，进入之后直接点击 **Install Shadowsocks Server** 按钮，运行脚本在服务器上安装Shadowsocks，稍等片刻安装完毕。

![image1](https://moshuqi.github.io/images/posts/vpn/19.png)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

安装完成后重新点击 **Shadowsocks Server** 选项，进入界面后便可看到 **Shadowsocks server** 的相关信息，主要有**加密方式**，**端口号**，**服务器密码**，后续客户端连接服务器需要用到这些信息。

![image1](https://moshuqi.github.io/images/posts/vpn/9.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

### **3.3 安装Shadowsocks客户端**

**Shadowsocks**客户端的[下载地址](https://shadowsocks.org/en/download/clients.html)，可以看到有各种客户端的下载。貌似这货也是得翻墙才能访问到。

![image1](https://moshuqi.github.io/images/posts/vpn/10.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

#### **3.3.1 Mac配置**

用的是Mac电脑，所以点击相关链接。东西都挂在github上，下载对应的zip文件，下载完成后安装并运行起来。

![image1](https://moshuqi.github.io/images/posts/vpn/11.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

点击图标，进入 **服务器设置**

![image1](https://moshuqi.github.io/images/posts/vpn/12.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

主要有四个地方要填，**服务器的地址**，**端口号**，**加密方法**，**密码**。服务器地址即为之前 **Main controls**选项中的IP地址。端口号、加密方法、密码必须与之前 **Shadowsocks Server** 中的信息一一匹配，否则会连接失败。

![image1](https://moshuqi.github.io/images/posts/vpn/13.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

设置完成后点击确定，然后服务器选择这个配置，默认选中PAC自动模式，确保Shadowsocks状态为**On**，这时候打开谷歌试试~

![image1](https://moshuqi.github.io/images/posts/vpn/18.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

Google图标右下角显示的是Canada，因为之前服务器的地址选的是加拿大：）

#### **3.3.2 iOS配置**

iOS上用的VPN App 是**Wingy**，可以App Store上直接搜。官方的**Wingy**下载是免费的，注意分辨有些图标相似的App。

下载完成后运行，点击 **选择线路**

![image1](https://moshuqi.github.io/images/posts/vpn/14.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

选择 **新增线路**

![image1](https://moshuqi.github.io/images/posts/vpn/15.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

选择 **Shadowsocks(R)**

![image1](https://moshuqi.github.io/images/posts/vpn/16.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

在配置界面填写服务器相关的信息，和Mac上的一样，填写完成后保存，然后在首页进行连接。

![image1](https://moshuqi.github.io/images/posts/vpn/17.jpeg)![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

这样一来手机也能愉快的翻墙了。当然其他端的配置方式也基本一致，可以根据使用的平台下载对应的客户端。下载好的客户端最后自己在别处备份一下，因为官网需要翻墙，以方便后续其他未翻墙的机器下载。

最后，自己搭建的 VPN 好处是可以和别人共享，告诉别人相关的配置信息即可。市面上一些收费的 VPN 还会有限制，比如说不让看 YouTube 有一定流量限制不能分享账号否则封号等。