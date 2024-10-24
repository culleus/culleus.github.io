---
title: SumatraPDF_settings
date: 2024-10-24 11:00:00 +0800
categories: [软件]
tags: [软件]
---

[SumatraPDF](https://www.sumatrapdfreader.org/free-pdf-reader)是一款轻便的pdf阅读器

以下为设置下划线和波浪线的快捷键的流程：

点开设置-高级选项，在打开的txt文档中找到Shortcuts，插入以下代码
```
[
		Cmd = CmdCreateAnnotUnderline
		Key = w, W
]
[
		Cmd = CmdCreateAnnotSquiggly
		Key = g, G
]
```
然后保存文档，即设置快捷键成功。加上自带的高亮标注，已有三种标注方式
