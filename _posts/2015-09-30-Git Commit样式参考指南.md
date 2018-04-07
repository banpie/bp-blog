---
layout: post
post_title: "Git Commit样式参考指南"
post_date: 2015-09-30 11:20
post_name: git-styleguide
tags: [开发,前端]
published: true
categories: 编程
---

关于Git Message的提交样式有很多理想的模版，本文参考Udacity的项目审核标准，结合自己实际的项目经验，提供下文的项目Commit样式指南。


在Commit Message的结构中，每一条Commit Message应该包含3个相互独立的部分，并通过空格区分开来：`标题`，`正文`，`脚注`。

举例如下：

	类型: 主题
	
	正文：
	
	脚注：

### 标题：类型
Commit Message的`类型`包含在`标题`之中，几大常见的类型如下：

- feat: 增加新的功能
- fix: 程序错误的修复
- docs: 对文档的修改
- style: 样式的修改；修改标点符号等等；无涉及代码的修改；
- refactor: 对Production Code的重构
- test: 增加测试代码，测试代码的重构；无涉及Production Code 的修改
- chore: 更新代码构建的任务，package manager的配置等等； 无涉及Production Code的修改


### 标题：主题
`主题`的描述文字不能超过50个字符，如果是英文描述其每个单词的首字母需要大写，并且结尾不能增加句号。

使用祈使句描述该条Commit所做的内容，不能使用过去时，比如应该用“改变”，而非“改变了”。

### 正文
并非所有的Commit都需要填写`正文`，只有当标题无法全部解释该Commit的内容的时候，才需要在`正文`中增加必要的解释；正文主要包括该commit所作的内容以及为什么这么做，也就是What和Why。

在撰写`正文`的规范中，应该在`标题`和`正文`之间增加一段空行，并且正文中每一行不要超过72个字符。

### 脚注
`脚注`也是非必需项，主要是用来跟踪错误ID（issue tracker IDs）。


### 举例

下文列出英文版Commit Message的例子：

	feat: Summarize changes in around 50 characters or less
	
	More detailed explanatory text, if necessary. Wrap it to about 72
	characters or so. In some contexts, the first line is treated as the
	subject of the commit and the rest of the text as the body. The
	blank line separating the summary from the body is critical (unless
	you omit the body entirely); various tools like `log`, `shortlog`
	and `rebase` can get confused if you run the two together.
	
	Explain the problem that this commit is solving. Focus on why you
	are making this change as opposed to how (the code explains that).
	Are there side effects or other unintuitive consequenses of this
	change? Here's the place to explain them.
	
	Further paragraphs come after blank lines.
	
	 - Bullet points are okay, too
	
	 - Typically a hyphen or asterisk is used for the bullet, preceded
	   by a single space, with blank lines in between, but conventions
	   vary here
	
	If you use an issue tracker, put references to them at the bottom,
	like this:
	
	Resolves: #123
	See also: #456, #789
