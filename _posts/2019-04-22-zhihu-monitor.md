---
ID: 3082
post_title: >
  创业公司品牌部如何自动化监测知乎问题的回答数变化
post_name: zhihu-monitor
author: 半撇
post_date: 2019-04-22 22:04:40
layout: post
link: http://www.banpie.info/zhihu-monitor/
published: true
tags:
  - 知乎
categories:
  - 营销
---
对于重视内容营销的公司来说，知乎应该是目前最具价值的营销平台了：**只要你好好的生产内容，你一定可以获得应有的营销回报**。

所以，你会看到越来越多的品牌入驻知乎，他们在知乎上开设了越来越多跟品牌相关的问题。比如每一次钉钉发布了新功能之后，品牌部门就会创建一个类似「如何看到钉钉发布了xx功能」的问题，然后邀请一些钉粉来回答。

那么，这么做有什么好处呢？

1.  **直接曝光**：随着越来越多知乎答主回答问题，就会有更多知乎用户会在时间线上面看到这个问题内容。
2.  **SEO优化**：因为知乎在搜索引擎的权重很高，如果有人搜索相关的关键词，相关的热门知乎问题更有可能出现在搜索引擎的前面。

在半撇私塾创立的第一年，我们开设了1期线下班，并且邀请了学员参与到了《[如何评价半撇私塾的全栈新媒体骇客训练营？ ][1]》的回答，自然目的也是很明确：**我们对于我们的教学质量非常有信心，因此我们也希望更多的潜在用户知道**。

但是实际上，第一次内测课程后，就没有让后面的付费学员去参与到这部分回答了。但是最近1年，同时总反馈有时候总会出现一些「莫名其妙」的恶意评价。

比如：

[<img class="alignnone size-full wp-image-3075" src="http://www.banpie.info/wp-content/uploads/2019/04/20190422211443.png" width="1280" height="574" alt="" />][2]

[<img class="alignnone size-full wp-image-3076" src="http://www.banpie.info/wp-content/uploads/2019/04/20190422211427.png" width="1280" height="608" alt="" />][3]

之所以形容为「莫名其妙」，是因为评价的内容丝毫跟我们的运营方式和课程内容毫无关系，所以一看就是知道并不是自己的学生。

**实际上，半撇私塾从来都不排斥「差评」**。我们把所有的满意度评价，原封不动的公开在了「[半撇私塾课程满意度公开评价表][4]」，这是我每一天都会查看无数遍的网站，因为我所有的课程优化灵感都来源于此。

但是问题来了：出现恶意评价的时候，品牌的同事不可能24小时去关注这个问题有没有更新，部门应该如何第一时间知道呢？

作为一个「Automate Everything」的推崇者，我开始思考：**有什么方式更自动化的方式呢**？

让我们来分析一下！这个问题的关键在于：在我无法判断在知乎问题下的新回答，是正常评价还是恶意评价的前提下，我如何实现「一旦新的回答，负责人就能收到及时通知」。

你可能会想「关注知乎问题」不就可以了，有更新就会在知乎的通知收到了啊。

但是，品牌的同事可能关注了上百个问题，每个问题可能定期都会有新的回答，这么多通知，又怎么能确保关注到了这一条评价问题呢？

于是，我开始观察知乎的页面结构。在标题的下面有一个「回答数」，这个就是关键！

一旦有新的回答，那么这个数字就会发生变化，那么只要发生变化，我就通过程序化的方式通知到对应的渠道不就可以了！

[<img class="alignnone size-full wp-image-3077" src="http://www.banpie.info/wp-content/uploads/2019/04/20190422212435.png" width="1280" height="703" alt="" />][5]

## 1\.监测知乎回答数的变化

因此破解这个问题的第一步，在于：寻找到能够监测知乎回答数的变化的工具。

对于常年有收集工具习惯的我来说，这是一个相对简单的过程：在线工具 [Wachete][6] 和 [Distill Web Monitor][7] 都能实现这样的功能。

如果你没有已知的工具，因为这个需求的关键词是「Web Monitor」或者「Data Monitor」，你也可以使用关键词去 Google 搜索对应的工具。

在这里我使用 Wachete 来介绍实现过程：你需要注册一个Wachete，然后添加需要监测的链接和内容，再设置对应的通知方式和监测时间频率即可。

[<img class="alignnone size-full wp-image-3078" src="http://www.banpie.info/wp-content/uploads/2019/04/20190422214011.png" width="1280" height="800" alt="" />][8]

## 2\.获取数据变化通知

有了第一步的监测以后，第二步骤的问题就是：**一旦数据有了变化，我如何收到通知呢**？

Wachete 已经有了内置邮件的通知了，但是因为半撇私塾内部都是在 Trello 协同的，而且不同的任务需要分配给不同的人（比如这一类品牌相关的问题就需要分配给营销部的同事）。

那么我如何更进阶的实现：**如果有新的数据变化，就自动在营销部生成一个卡片，并且分配给负责品牌的同事呢**？

这里你可以使用 [Trello Email to Board ][9]的功能，因为每个人在每个面板都有一个专属的邮件地址，只要发送这个任何内容到这个邮件地址，就自动生成卡片，并分配个这个人。

[<img class="alignnone size-full wp-image-3079" src="http://www.banpie.info/wp-content/uploads/2019/04/20190422213656.png" width="578" height="1280" alt="" />][10]

当然，如果你需要设置 Trello 卡片截止日期、自动添加 Trello「卡片的待办事项」，那么你就可以使用更强的Zapier 的工具，通过 Zapier 把 Wache 和 Trello 对接起来。

[<img class="alignnone size-full wp-image-3080" src="http://www.banpie.info/wp-content/uploads/2019/04/20190422220157.png" width="1280" height="732" alt="" />][11]

[<img class="alignnone size-full wp-image-3081" src="http://www.banpie.info/wp-content/uploads/2019/04/20190422213843.png" width="1280" height="847" alt="" />][12]

## 结语

我记得在研究生的期间，《危机公关》的课上老师说过：**当你的企业足够透明，那么就没有危机公关的说法**。

因为对待负面的内容，你应该反思，应该解决，并且把解决的过程用最透明、最实时的方式告诉你的用户。

让你的用户知道：**他们的意见和反馈是被无比重视的**。

所以，在这一篇文章的最后，也希望分享自己的经验和心得：**当一个真正的用户不通过内部渠道去吐槽你，而是在社交媒体吐槽你的时候，一定是你堵住了用户的嘴，让他没有渠道发泄**。

所以，要反思的永远是企业自身。

关于「危机公关」，如果你也遇到过一些有趣的、好玩的、聪明的、值得分享的经验和技巧，也欢迎你评论跟我分享。

 [1]: https://www.zhihu.com/question/51557855
 [2]: http://www.banpie.info/wp-content/uploads/2019/04/20190422211443.png
 [3]: http://www.banpie.info/wp-content/uploads/2019/04/20190422211427.png
 [4]: https://www.bpteach.com/review/
 [5]: http://www.banpie.info/wp-content/uploads/2019/04/20190422212435.png
 [6]: https://www.wachete.com/
 [7]: https://chrome.google.com/webstore/detail/distill-web-monitor/inlikjemeeknofckkjolnjbpehgadgge
 [8]: http://www.banpie.info/wp-content/uploads/2019/04/20190422214011.png
 [9]: https://help.trello.com/article/809-creating-cards-by-email
 [10]: http://www.banpie.info/wp-content/uploads/2019/04/20190422213656.png
 [11]: http://www.banpie.info/wp-content/uploads/2019/04/20190422220157.png
 [12]: http://www.banpie.info/wp-content/uploads/2019/04/20190422213843.png