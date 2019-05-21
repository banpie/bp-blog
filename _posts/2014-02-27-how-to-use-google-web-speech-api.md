---
ID: 122
post_title: >
  如何利用Google实现语音转录文本
post_name: how-to-use-google-web-speech-api
author: 半撇banpie
post_date: 2014-02-27 20:56:24
layout: post
link: >
  https://www.banpie.info/how-to-use-google-web-speech-api/
published: true
tags: [ ]
categories:
  - 工具
---
@蘑菇：我想要安装用嘴巴念就可以生成文字的软件，这样我写废话文章的时候的时候就不用打字打到手酸…

@山中小石头：经常地铁上有时候需要回复一份紧急邮件，拿着手机打字输入好痛苦，用微信又只能查看语音的文本内容，有什么好的工具，能直接把说的话转成文字吗？

音频转文本的功能，现在许多公司都在做，国内的百度语音搜索、搜狗的语音输入、微信的对话转文本、科大讯飞的语音识别，国外有苹果的Siri、Nuance，还有Google。

今天讲的就是Google 的Web Speech API，虽然这款产品还是在内测的阶段，但是区别与微信、百度或者搜狗的其他同类产品，功能足够强大了：

*   支持超长时间的录音（目前测试好像没有时间限制

*   支持32种语言的录音转文

*   识别能力超强（除了一些品牌名称无法很好识别之外，日常对话零失误识别

*   支持一键复制粘贴和直接创建发送Email，这样以来，出门在外有急事要发邮件，对着手机麦克风说说就行了

## 1、手机访问Web Speech API

用手机Chrome浏览器访问：<http://t.cn/zjgwkHW>。

[<img class="alignnone size-full wp-image-25031670" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-1083/0-86.jpg" width="620" height="952" alt="" />][1]

## 2、选择录音语言

点击输入框底部的「语言选择条」，在弹出的菜单中选择你的录音语言。

[<img class="alignnone size-full wp-image-25041671" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-1093/0-87.jpg" width="620" height="475" alt="" />][2]

## 3、对着手机麦克风说话

点击输入框右侧的「麦克风」按钮，之后会在底部弹出黄色的「使用麦克风」确认对话框，点击确认后，对着麦克风说话即可。

[<img class="alignnone size-full wp-image-25061672" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-1113/0-88.jpg" width="576" height="884" alt="" />][3]

## 4、复制文本或发送邮件

录音完毕后，再次点击输入框右侧的「麦克风」按钮，即可完成语音文本转录。此后，下方会出现两个按钮，点击「Copy and paste」后，在输入框中的文本即可进行复制，点击「Create Email」可直接创建一个带录音文本的邮件。

[<img class="alignnone size-full wp-image-25071673" src="http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-1123/0-89.jpg" width="620" height="476" alt="" />][4]

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg0NDA4NTU3NV19
-->

 [1]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-108.jpg
 [2]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-109.jpg
 [3]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-111.jpg
 [4]: http://www.banpie.info/wp-content/uploads/2019/04/unnamed-file-112.jpg
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NzkzNDE1MTVdfQ==
-->