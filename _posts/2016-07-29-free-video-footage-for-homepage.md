---
ID: 325
post_title: 五大可免费商用的高清视频库
post_name: free-video-footage-for-homepage
author: 半撇
post_date: 2016-07-29 00:00:00
layout: post
link: >
  https://www.banpie.info/free-video-footage-for-homepage/
published: true
tags:
  - 影视
categories:
  - 未分类
---
> 源码传送门：我在Codepen也建立的[Sample Code][1]

是不是看到许多网站的头部都是这种带着视频背景，酷酷的样子？

[<img class="alignnone size-full wp-image-2968" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-4.gif" width="600" height="419" alt="xgclass.com" />][2]

今天解决两个问题： 1. 我不懂拍摄，也没有好设备，那哪里找到可以免费商用的视频素材？ 2. 怎么把这种视频放到网站做背景呢？

## No.5: Coverr

> *   简介：Covers 通常每周会上架7个新的视频，视频的分类会比Pexels稍微少一点，但是如果是初创的互联网企业，Tech哪个类别的素材要比Pexels好很多。
> *   链接：<http://coverr.co/>

![Coverr Screenshot][3]

## No.4: Videovo

> *   简介：庞大的素材库，有超过3000的视频素材，除了高清视频素材还有动画素材，相对其他素材站比较好的一点是，你可以根据素材关键字和热门度进行检索。
> *   链接：<http://www.videvo.net/>

![videvo Screenshot][4]

## No.3: Wedistill.io

> *   简介：技术服务公司Create The Bridge的子项目，每10天会上架10段视频，全是免费高清的广告素材。
> *   链接： <http://wedistill.io/>

![wedistill.io Screenshot][5]

### No.2: Pexels

> *   简介：Pexels 拥有大量的免版权的高清素材库（CC0协议｜不用署名也不用付费），按列别主要分为：动物、街道、山川、延时、模糊、食物、城市、饮料、天空等等。你可以把其中的视频放到官方网站、销售引导页以及任何的商业项目中。虽然东西都是免费，但是质量都是极高的。你可以通过邮件实时订阅他们的素材更新。
> *   链接： <http://videos.pexels.com/>

![videos.pexels.com Screenshot][6]

## No.1: MAZWAI

> *   简介：这是我最喜欢的视频库了，主要集中在风景、建筑主题上，虽然没有严格的分类，但是每一段高清素材都是电影级别的质感。
> *   链接：<http://mazwai.com/#/videos>

[<img class="alignnone size-full wp-image-2969" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-362.jpg" width="1280" height="714" alt="mazwai.com/#/videos Screenshot" />][7]

下载了视频以后，把视频上传到七牛，这个在之前[中文世界最良心的视频托管工具][8]中已经分享过了，然后你可以在首页的banner处添加对应的代码，下面提供参考，如果你是在不懂，我在Codepen也建立的[Sample Code][1]，希望给你提供一点灵感。

        <div class="homepage-hero-module">
            <div class="video-container">
                <div class="filter"></div>
                <video autoplay loop class="fillWidth">
                    <source src="http://cdn.xgclass.com/Busy.mp4" type="video/mp4" />Your browser does not support the video tag. I suggest you upgrade your browser.
                    <source src="http://cdn.xgclass.com/Busy.webm" type="video/webm" />Your browser does not support the video tag. I suggest you upgrade your browser.
                </video>
                <div class="poster hidden">
                    <img src="http://xgclass.com/xgclass/wp-content/uploads/2016/07/headerbg.jpg" alt="">
                </div>
            </div>
        </div>

 [1]: http://codepen.io/devmidai/full/EypjxW/
 [2]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-4.gif
 [3]: https://s0.wordpress.com/mshots/v1/coverr.co?w=400&h=300
 [4]: https://www.layerthemes.com/wp-content/uploads/2015/09/Videvo.jpg
 [5]: https://s0.wordpress.com/mshots/v1/wedistill.io?w=400&h=300
 [6]: https://s0.wordpress.com/mshots/v1/videos.pexels.com?w=400&h=300
 [7]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-362.jpg
 [8]: http://www.banpie.info/qiniu-cloud-storage