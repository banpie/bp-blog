---
post_title: ChangeLog应该怎么写？
post_date: 2017-05-04
post_name: how-to-write-changelog
categories: 技术
tags: [changelog,技术文档]
published: true
categories: 编程
---

> 在工作中需要写很多课程文档，随着不断的迭代，内容也会不断的变化，时间一长，就很可能忘记之前在什么时候做过什么改动了，所以这个时候就需要文档的写作者保持更新 Changelog 来确保每一个协作者都在同一个步伐。

很多人认为更新日志好像是只有「写代码」才需要的一个文档，但是只要涉及到文档协同、对1个文档进行长期的迭代，我们都需要一个更新文档来记录历史变动，这样新的人进来就可以对整个来龙去脉有一个非常直观的了解。

## 什么是更新日志

那什么是更新日志呢？更新日志（Change Log）是一个由人工编辑，以时间为倒叙的列表。 这个列表记录所有版本的重大变动。

我们来看一个直观的案例。

```

# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

## [Unreleased]
### Added
- zh-CN and zh-TW translations from @tianshuo.
- de translation from @mpbzh.
- it-IT translation from @roalz.
- sv translation from @magol.
- tr-TR translation from @karalamalar.
- fr translation from @zapashcanon.

### Changed
- Start versioning based on the current English version at 0.3.0 to help
translation authors keep things up-to-date.
- Fix typos in zh-CN translation.
- Fix typos in pt-BR translation.

## [0.3.0] - 2015-12-03
### Added
- RU translation from @aishek.
- pt-BR translation from @tallesl.
- es-ES translation from @ZeliosAriex.

## [0.2.0] - 2015-10-06
### Changed
- Remove exclusionary mentions of "open source" since this project can benefit
both "open" and "closed" source projects equally.

## [0.1.0] - 2015-10-06
### Added
- Answer "Should you ever rewrite a change log?".

### Changed
- Improve argument against commit logs.
- Start following [SemVer](http://semver.org) properly.

## [0.0.8] - 2015-02-17
### Changed
- Update year to match in every README example.
- Reluctantly stop making fun of Brits only, since most of the world
  writes dates in a strange way.

### Fixed
- Fix typos in recent README changes.
- Update outdated unreleased diff link.

## [0.0.7] - 2015-02-16
### Added
- Link, and make it obvious that date format is ISO 8601.

### Changed
- Clarified the section on "Is there a standard change log format?".

### Fixed
- Fix Markdown links to tag comparison URL with footnote-style links.

## [0.0.6] - 2014-12-12
### Added
- README section on "yanked" releases.

## [0.0.5] - 2014-08-09
### Added
- Markdown links to version tags on release headings.
- Unreleased section to gather unreleased changes and encourage note
keeping prior to releases.

## [0.0.4] - 2014-08-09
### Added
- Better explanation of the difference between the file ("CHANGELOG")
and its function "the change log".

### Changed
- Refer to a "change log" instead of a "CHANGELOG" throughout the site
to differentiate between the file and the purpose of the file — the
logging of changes.

### Removed
- Remove empty sections from CHANGELOG, they occupy too much space and
create too much noise in the file. People will have to assume that the
missing sections were intentionally left out because they contained no
notable changes.

## [0.0.3] - 2014-08-09
### Added
- "Why should I care?" section mentioning The Changelog podcast.

## [0.0.2] - 2014-07-10
### Added
- Explanation of the recommended reverse chronological release ordering.

## 0.0.1 - 2014-05-31
### Added
- This CHANGELOG file to hopefully serve as an evolving example of a standardized open source project CHANGELOG.
- CNAME file to enable GitHub Pages custom domain
- README now contains answers to common questions about CHANGELOGs
- Good examples and basic guidelines, including proper date formatting.
- Counter-examples: "What makes unicorns cry?"

[Unreleased]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.3.0...HEAD
[0.3.0]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.2.0...v0.3.0
[0.2.0]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.1.0...v0.2.0
[0.1.0]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.0.8...v0.1.0
[0.0.8]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.0.7...v0.0.8
[0.0.7]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.0.6...v0.0.7
[0.0.6]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.0.5...v0.0.6
[0.0.5]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.0.4...v0.0.5
[0.0.4]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.0.3...v0.0.4
[0.0.3]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.0.2...v0.0.3
[0.0.2]: https://github.com/olivierlacan/keep-a-changelog/compare/v0.0.1...v0.0.2
```
## 为什么需要更新日志

简单来说，当一群人一起工作的时候，特别是在同一篇文档工作的时候，我们便需要让协作者更好知道每一个版本有哪些区别。

## 如何写好更新日志

明确了什么是更新日志，以及为什么需要更新日志，我想更重要的应该是如何写好一篇更新日志了。

[Keepachangelog.com](http://keepachangelog.com/) 是一个致力于规范更新日志的项目，在网站中他提及了：

> 貌似GNU或者GNU NEWS还是提过些规范的，事实是它们太过简陋了。 开发有那么多种情况，采用那样的规范，确实是不太合适的。

所以项目的发起人认为之前的世界标准并不是足够优质，所以他自己制作了对应的 [规范](https://github.com/olivierlacan/keep-a-changelog/blob/master/CHANGELOG.md) 发布在Github上，在项目中他是这么定义一份优秀的更新日志的：

- 给人而不是机器写的。记住，要说人话。
- 快速跳转到任意段。所以采用markdown格式
- 一个版本对应一个章节。
- 最新的版本在上，最老的在下面。
- 所有日期采用'YYYY-MM-DD'这种规范。（例如北京奥运会的2008年8月8日是2008-08-08）这个是国际通用，任何语言 都能理解的，并且还被[xkcd](http://xkcd.com/1179/)推荐呢！
- 标出来是否遵守[语义化版本格式](http://semver.org/lang/zh-CN/)
- 每一个软件的版本必须：
  - 标明日期（要用上面说过的规范）
  - 标明分类（采用英文）。规范如下git：
  - 'Added' 添加的新功能
  - 'Changed' 功能变更
  - 'Deprecated' 不建议使用，未来会删掉
  - 'Removed' 之前不建议使用的功能，这次真的删掉了
  - 'Fixed' 改的bug
  - 'Security' 改的有关安全相关bug

另外关于命名规范，他也建议直接将更新日志命名为：`CHANGELOG.md`，注意大小写。

> 像`HISTORY.txt`, `HISTORY.md`, `History.md`, `NEWS.txt`, `NEWS.md`, `News.txt`, `RELEASES.txt`, `RELEASE.md`, `releases.md`这么 多文件名就太不统一了。


