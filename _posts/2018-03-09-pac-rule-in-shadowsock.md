---
ID: 418
post_title: >
  翻墙进阶术：如何让你访问普通外网的速度快人一步
post_name: pac-rule-in-shadowsock
author: 半撇banpie
post_date: 2018-03-09 00:00:00
layout: post
link: >
  https://www.banpie.info/pac-rule-in-shadowsock/
published: true
tags: [ ]
categories:
  - 效率
---
随着政府对于VPN的管控，「翻墙」似乎已经互联网人必须要具备的基础技能了。

如果你不太熟悉这个词语的话，简单的来说，所谓「翻墙」就是「跨过一些网络的限制，自由的访问互联网上的信息」。它就好比，你读小学的时候，学校的墙后有一间网吧，学校规定说所有学生都不许去网吧，有一天你因为需要查资料或者打游戏，偷偷的跑去了，我们把你这种行为称之为「翻墙」。

你可能会问：为什么要翻墙呢？就好比网吧一样，在开放自由的网络的世界里，你可以做很多好事，也可以做很多坏事，但是你不能说它可能用来「做坏事」，就剥脱你这个权利。

说到「翻墙」的好处自然有很多，但是光是能够访问 Youtube 和 Google 的系列产品，其实已经足够说服你掌握这项技能了。

而至于如何翻墙的问题，如果你愿意搜索，你很容易就能找到许多工具和技巧，简单的比如下载蓝灯（不稳定，但免费），稍微复杂一些的比如“一键Shadowsocks”（如果你不知道这个，你可以查看[如何翻墙：使用Shadowsock搭建一条自由的梯子][1]）。

但是本文说的不是如何翻墙，而是使用代理服务器翻墙以后，许多人在「自动代理模式」和「全局代理模式」下可能遇到的一个问题。

在这里之前，我们先来说说什么是「自动代理模式」。所谓「自动代理模式」，也称「PAC模式」。在这种模式下，代理服务器会在访问网络的时候，会读取一个叫做「PAC文件」里的规则（也就是 GFWList 里被墙的网站列表），来确定你访问的网站有没有被墙。如果发现你访问的网站在这个「PAC文件」的列表里，那么就使用代理服务器访问，如果没有就使用你本地网络访问。

而区别「自动代理模式」对访问的网站做一个事先的预判，「全局代理模式」则是一锅端，无论你是外国网站还是中国网站，统统都走代理服务器来访问。

上网的时候，通常情况下，我都会选择「自动代理模式」，只有遇到某一些外国网站，虽然打得开，但是速度慢的时候，我才会切换到「全局代理模式」，但是一旦使用完毕，我又要切换回「自动代理模式」，不然你用外国服务器来访问国内的网站会很卡。

所以，这样就出现了一个困境：**那些不在「黑名单」的外国网站，如果我用「自动代理模式」去访问，就会很慢，但是如果我切换到「全局代理模式」访问，每一次使用后又要切换回来，实在是太麻烦了。**

有没有什么办法，比如我经常访问 Trello.com，Zapier.com，这些网站是不在「黑名单」的，但是又可以让代理服务器在自动代理模式下走外网的流量呢？

其实，答案其实就隐藏在「Pac」中！如果「自动代理模式」是访问前先查询一下这个网站是否在「PAC文件」里的规则，那么我只要把 Trello.com，Zapier.com 等这些网站加入到规则里不就行了吗？

所以问题就落到了「如何添加Pac规则」这个上面了，下面以 Shadowsock 客户端为例子，介绍如何把我常用的网站添加到 Pac 规则中。

1.  打开Shadowsock 客户端，切换到「自动代理模式」，并打开「编辑PAC用户自定义规则」（这个就是代理服务器帮你决定哪些网站走代理，哪些不走代理的「筛子」） [<img class="alignnone size-full wp-image-2545202" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-1433/006tKfTcgy1fpjlw262lcj30pc0g60tr.jpg" width="912" height="582" alt="" />][2]
2.  点击后就会出现一个编辑窗口，我们就需要在这里输入规则，比如你希望你访问的Trello.com的时候都走代理，那么就输入「||trello.com^」，如果是Zapier.com，就输入「||zapier.com^」，保存后重启客户端即可。 [<img class="alignnone size-full wp-image-2547203" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-1453/006tKfTcgy1fpjm2g6fiyj30qm0g4jrh.jpg" width="958" height="580" alt="" />][3]

另外，这里需要补充一下规则的基本语法，比如在`||trello.com^`中，前面的`||`号就是「域名标示」，它表示如果是`||trello.com`，那么无论是http://tello.com、https://trello.com 还是 ftp://trello.com等前缀的地址均满足条件。而`^`注意则是结尾标示，意思是要么在这个符号的地方结束。

[<img class="alignnone size-full wp-image-2549204" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-1473/006tKfTcgy1fpjlzqqi6bj319u0iegm8.jpg" width="1280" height="513" alt="" />][4]

还有一个比较有意思的是，你会发现有时候我已经明明把Trello放进去了Pac里面，为什么网站打开还是慢了？这就牵涉到“引用资源”的问题了，也就是你打开Trello网站的时候，访问的不仅仅来自`Trello.com`这个域名下的资源，他的图片可能是放在亚马逊服务器上的（AWS），他的JS文件可能是来自Google的……。

因此，我们可以借助Chrome的开发者工具看一下（快捷键`F12`），先切换到「Network」中，看一看在加载这一个网页的时候，哪一些资源访问的速度比较慢？URL的域名是什么？再把域名统统添加到Pac规则中去。

[<img class="alignnone size-full wp-image-2552205" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-1483/006tKfTcgy1fpjmsst51cj31kw0u70wb.jpg" width="1280" height="679" alt="" />][5]

[<img class="alignnone size-full wp-image-255206" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-1523/006tKfTcgy1fpjmt6vzrej31kw0hjgo6.jpg" width="1280" height="394" alt="" />][6]

通过上面的案例，我们发现在访问的Trello的网站中，主要的资源不仅有`Trello.com`，例如CSS的文件是来源于`trellocdn.com`这个域名，因此我们在Pac规则中再写一条`||trellocdn.com^`即可。

<!--stackedit_data:
eyJoaXN0b3J5IjpbNTE2NzAwMzUwXX0=
-->

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY4ODk0OTQxNl19
-->

 [1]: https://www.banpie.info/shadowsocks-pac-gfw/
 [2]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-143.jpg
 [3]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-145.jpg
 [4]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-147.jpg
 [5]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-148.jpg
 [6]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-152.jpg [1]: https://www.banpie.info/shadowsocks-pac-gfw/
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjc4ODMxNDQ3XX0=
-->