---
ID: 3052
post_title: >
  创业团队如何使用 Butler
  来自动化 Trello
post_name: butler-for-trello
author: 半撇
post_date: 2019-04-10 23:08:39
layout: post
link: >
  http://www.banpie.info/butler-for-trello/
published: true
tags:
  - trello
categories:
  - 工具
---
在我私藏的 826 条神器工具中，如果说我要推荐其中最实用的一个，那么当属 Trello 了！在我一天8 小时工作中，虽然使用的工具非常多，比如：Chrome+各类插件、钉钉、微信、语雀、石墨、金数据、Zapier、Mautic、Typora、Github……，但是超过50%的时间，我都在 Trello 中进行的。

但是今天的文章中，我并不是要推荐 Trello（之前也写过了一篇 [像专家一样使用Trello][1] 的文章），而是分享我在 使用 Trello 的过程中，我如何自动化处理一些常见的工作。

先来说说背景。

## 为什么要在 Trello 中使用 Butler

半撇私塾的任务管理都是基于 Trello 面板，在面板中，我们根据任务的进度划分为不同的「列表」（Lists）：

1.  Idea
2.  To Do
3.  Doing
4.  On Hold
5.  Done

[<img class="alignnone size-full wp-image-3053" src="http://www.banpie.info/wp-content/uploads/2019/04/20190410223637-1.png" width="1280" height="786" alt="" />][2]

在「列表」下面，有不同的任务卡片，关于这个任务卡片的所有描述、截止时间设置、负责人、讨论，我们都会在卡片中进行。

[<img class="alignnone size-full wp-image-3054" src="http://www.banpie.info/wp-content/uploads/2019/04/20190410223718-1.png" width="1280" height="781" alt="" />][3]

但是问题是，每一个卡片都有截止日期，通常来说，当我们把卡片从「Doing」拖动到「Done」的时候，应该要把「截止日期」勾选掉才对，这样才表示「我把这个任务做完了」。

[<img class="alignnone size-full wp-image-3055" src="http://www.banpie.info/wp-content/uploads/2019/04/20190410223609-1.png" width="1280" height="791" alt="" />][4]

但是，实际过程中，同事总是忘记把「截止日期」字段勾选掉，所以出现了一排红红的、看着令人难受的符号。

[<img class="alignnone size-full wp-image-3056" src="http://www.banpie.info/wp-content/uploads/2019/04/20190410223926-1.png" width="1280" height="788" alt="" />][5]

每一次都在卡片中提醒同事：「完成后记得勾选截止日期哦」，这显然不是一个非常聪明的办法！

所以我想，有没有什么办法能够实现：如果同事把卡片拖动到「Done」，那么下面所有的卡片的截止日期就自动设置为「完成」呢？

利用「Trello Automation」等关键词，我终于找到了 [Butler][6]。

## 如何使用 Butler

你可以把 Butler 理解为 Trello 内的 [IFTTT][7]，这个工具旨在让帮助 Trello 用户免于重复性任务。例如我上面提及的的：如果同事把卡片拖动到「Done」，那么「Done」列表下所有的卡片的截止日期就自动设置为「完成」呢？

让我们直接进入 [软件][8] 页面看一下，我如何实现我上面的需求。

1\.**添加 Butler**：选择你所要设置自动化的面板，点击「Invite Butler」，把这个自动化机器人添加到你的 Trello 面板中。

[<img class="alignnone size-full wp-image-3057" src="http://www.banpie.info/wp-content/uploads/2019/04/20190410224929-1.png" width="1280" height="793" alt="" />][9]

2\.**添加 Butler 规则**：进入配置页面后，点击「Add Command」开始配置规则。

[<img class="alignnone size-full wp-image-3058" src="http://www.banpie.info/wp-content/uploads/2019/04/20190410225235-1.png" width="1280" height="785" alt="" />][10]

3\.**配置 Butler 规则**：在这里有无数的规则可以设定，你可以自己选择条件，和对应条件后续的执行动作，比如我这里设定的「如果有卡片移动到`Done`，那么截止日期设定为`Complete`」。

[<img class="alignnone size-full wp-image-3059" src="http://www.banpie.info/wp-content/uploads/2019/04/20190410225354-1.png" width="1280" height="784" alt="" />][11]

配置成功以后，你会发现面板中多了一个 BulterBot 的小人，一旦有卡片拖动到 Done，这个小人就会在卡片中评论：「I Marked the due date as complet in card xxx」。

[<img class="alignnone size-full wp-image-3060" src="http://www.banpie.info/wp-content/uploads/2019/04/20190410225718-1.png" width="1280" height="681" alt="" />][12]

Butler 的想象力是无限的，我也是一开始摸索，后面应该还有会很多Hack 小技巧，如果你也有一些常见的规则设定，也欢迎你评论跟我分享！

[1]: https://www.banpie.info/trello-keyboard-shortcuts/
[2]: http://www.banpie.info/wp-content/uploads/2019/04/20190410223637-1.png
[3]: http://www.banpie.info/wp-content/uploads/2019/04/20190410223718-1.png
[4]: http://www.banpie.info/wp-content/uploads/2019/04/20190410223609-1.png
[5]: http://www.banpie.info/wp-content/uploads/2019/04/20190410223926-1.png
[6]: https://butlerfortrello.com/
[7]: https://ifttt.com/
[8]: https://www.butlerfortrello.com/dashboard.html
[9]: http://www.banpie.info/wp-content/uploads/2019/04/20190410224929-1.png
[10]: http://www.banpie.info/wp-content/uploads/2019/04/20190410225235-1.png
[11]: http://www.banpie.info/wp-content/uploads/2019/04/20190410225354-1.png
[12]: http://www.banpie.info/wp-content/uploads/2019/04/20190410225718-1.png
