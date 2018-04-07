---
post_title: 半自动的海报生成术：如何提升30倍的的封面制作效率
post_date: 2018-03-09
post_name: how-to-design-cover-more-effectively
published: true
---

每一天做写一篇文章只有差不多1个多小时的时间，所以不会花太多时间在制作封面上，因此基本你看到文章的封面都是呈现这种统一的「模版风格」：

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fpksx35pgwj30rs0hzgno.jpg)

它比以前的纯色封面设计，其实多了就是现在设计中比较流行的「渐变色」。这主要是因为我在 Dribble 逛的时候，经常看到这类非常 Geek 感十足的设计，因此才开始在 Sketch 中将这类元素尝试融合到了文章的封面中。

![](https://ws1.sinaimg.cn/large/006tKfTcgy1fpksv627eaj30k00g3js0.jpg)

**但是，在 1 个月前，我制作一张封面花费大概5分钟时间**。这个繁琐的步骤是这样的：

1. **创建背景画布**：从Unsplash下载一张图片，在Sketch中裁剪成 900px*500px 的尺寸；
2. **添加暗色蒙层**：在图片上添加一层60%左右的黑色蒙层；
3. **添加渐变蒙层**：在图片上添加一层60%左右的黑色蒙层；
4. **添加文案标示**：把标题添加上去（Logo位置基本是固定不变的）；

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fpks52h9egj315o0c4t9w.jpg)

虽然4个步骤看起来很简单，但是其中还有非常大的优化空间，繁琐的步骤主要集中在第1步和第3步：

![](https://ws4.sinaimg.cn/large/006tKfTcgy1fpksgk3s98j315o0c4gmt.jpg)

- **第1步**：「创建背景画布」环节，每一次都要手动去 Unsplash 下载，再黏贴到 Sketch 中，这需要花费2分钟的（**也就是总耗时5分钟的40%**）；
- **第3步**：「添加渐变蒙层」环节，因为我不太确定什么样的渐变色比较好搭配，所以每一次都需要去照一张案例图，然后取色，再到Sketch中去配色，这个需要花费2.5分钟（**也就是总耗时5分钟的50%**）。

这两个环节是大量的人工操作，你想一想，如果可以把这2个环节也像第2步的「添加渐变蒙层」固定住，或者说「自动化」，**那么按照每1周需要制作4张封面图片的前提下，一年可以节省下936分钟的时间去做其他事**！

 而要做到这个「自动化」，就意味着我需要 Sketch 自动帮我完成2件事情：

1. 自动在900*500的画布中，插件一张 Unsplash 的随机图片；
2. 自动在这一张随机图片上添加上「业界通用」的渐变色；

因此，我用了「sketch auto unsplash」和「sketch auto gradient」找到了两个神级的工具：

- Unplash It Plugin 插件（https://github.com/fhuel/Unsplash-It-Sketch）
- UIgradient Template（https://gumroad.com/l/gradients）

安装到 Sketch 后，现在，整个工作流是这样的：

1. 在Sketch 中复制一张旧图片。
  ![](https://ws3.sinaimg.cn/large/006tKfTcgy1fpkt3nz9gdj310u08kq45.jpg)

1. 按住`Ctrl+Shift+U`后，Unplash It Plugin 插件会自动帮我从 Unsplash下载一张图片替换进来；
   ![](https://ws1.sinaimg.cn/large/006tKfTcgy1fpktqgq7boj315o0nzgpa.jpg)

1. 从 UIgradient Template 直接选择流行的渐变色添加上去；
   ![](https://ws4.sinaimg.cn/large/006tKfTcgy1fpktqv57puj31kw14mq6u.jpg)

1. 将旧标题替换为新标题。
   ![](https://ws2.sinaimg.cn/large/006tKfTcgy1fpktkooe59j31d00qun1k.jpg)


**现在制作一张封面，核心的工作就是按2个按钮、复制黏贴标题和导出的操作，过程花费不到10秒钟的时间。**

当然，这个还不是我非常满意的方案。我在想，既然布局是固定的，需要手动修改的只有标题，那么有没有可能能够实现：**只需我把标题输入到一个表单，然后表单的Webhook接口，利用Zapier整合Unsplash+Uigraident+Google Slide + Onedrive的API，自动生成1张封面图片，保存到我的Onedrive文件夹呢？**

应该是有可能的，不过等到我找到了方法在和你说吧。
