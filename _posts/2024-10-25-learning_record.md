---
title: 1025_learning_record
date: 2024-10-25 17:20:00 +0800
categories: [learn]
tags: [learn, 软件]
---

## tor 浏览器
首先是tor的下载，我选择的是通过telegram的[gettor机器人](https://t.me/gettor_bot)获取exe文件，下载到电脑上，然后安装好。

打开tor浏览器，配置tor网络（失败）：由于身处墙内，选择使用代理，并使用官方提供的网桥，只需输入验证码，再点击复制，粘贴到替换网桥，测试tor网络连接，失败。

## 复现论文

title:[Environment and microbiome drive different microbial traits and functions in the macroscale soil organic carbon cycle](https://doi.org/10.1111/gcb.17465)

DOI:[https://doi.org/10.1111/gcb.17465](https://doi.org/10.1111/gcb.17465)

R语言脚本和原始数据在[这里](https://www.research-collection.ethz.ch/handle/20.500.11850/685531)

从[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/CRAN/)下载R 4.4.1 base以及 Rtools44，下载[rstudio](https://posit.co/download/rstudio-desktop/) ，打开rstudio，设置清华镜像下载package
```
options("repos" = c(CRAN="https://mirrors.tuna.tsinghua.edu.cn/CRAN/"))
```
然后按其脚本文件安装各种包，但有两个安装失效 [swfdr](https://bioconductor.org/packages/release/bioc/html/swfdr.html)和[phyloseq](https://bioconductor.org/packages/release/bioc/html/phyloseq.html)，需要在biocmanager中安装
```
if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install("swfdr")
BiocManager::install("phyloseq")
```
## 从ncbi中下载sra

[^footnote]
教程参考：
[^footnote]:http://www.yingbio.com/article-35507-204466.html
