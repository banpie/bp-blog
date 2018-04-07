---
layout: post
post_title: Git Commit 应该怎么写？
post_date: 2017-05-07
post_name: how-to-write-git-commit-message
categories: 技术
tags: [Git,技术文档]
published: true
categories: 编程
---

在使用Git 进行版本控制的时候，我们需要提交对应的 Commit 信息，这一块与 Changelog 的写作有一些类似，这一篇文章就介绍 Commit Message 的核心结构和规范。

### 提交信息的结构

一条 commit 信息通常包括3个部分：

```
type: subject

body

footer
```

### Type：类型

具体来说，Type 分为：

- **feat:** 增加新功能；
- **fix:** 修复错误；
- **docs:** 修改文档；
- **style:** 修改样式；
- **refactor:** 代码重构；
- **test:** 增加测试模块，不涉及生产环境的代码；
- **chore:** 更新核心模块，包配置文件，不涉及生产环境的代码；

### Subject：标题

标题不超过50个字符，结尾不需要对应的句号；应该使用祈使句来描述，比如：修复标点符号错误。

### Body：正文

并不是所有的 Commit 都需要正文，所以这一模块是可选的，必要的时候对本次 Commit 做一些背景说明，阐释具体的原因和内容，但是不解释具体的过程。

注意：正文的文字不能超过72个字符。

### Footer：结尾

结尾是可选的，通常来说可以添加对一些错误信息ID的补充。

### Example：举例

```
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
```