---
title: learning_record_1025
date: 2024-10-25 17:20:00 +0800
categories: [learn]
tags: [learn]
---

## tor 浏览器
首先是tor的下载，我选择的是通过telegram的[gettor机器人](https://t.me/gettor_bot)获取exe文件，下载到电脑上，然后安装好。

打开tor浏览器，配置tor网络（失败）：由于身处墙内，选择使用代理，并使用官方提供的网桥，只需输入验证码，再点击复制，粘贴到替换网桥，测试tor网络连接，失败。
解决方法：用代理连，先关掉V2rayN的流量嗅探，然后根据[这个](https://nodebe4.github.io/opinion/2020-07-31/%E5%A6%82%E4%BD%95%E7%94%A8%E5%89%8D%E7%BD%AE%E4%BB%A3%E7%90%86%E8%AE%BF%E9%97%AETor%E6%B5%8F%E8%A7%88%E5%99%A8-%E4%BB%A5%E4%B8%BB%E6%B5%81%E7%BF%BB%E5%A2%99%E8%BD%AF%E4%BB%B6%E4%B8%BA%E4%BE%8B/)进行配置。

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

下载[SRAToolkit](https://github.com/ncbi/sra-tools/wiki/01.-Downloading-SRA-Toolkit)，解压到本文件夹，配置。

在ncbi中下载Accession list，在cmd中输入<br>
```
prefetch.exe --option-file SRR_Acc_List.txt
```

即可下载<br>
此时下载得到的文件为sra格式，需要转化为fastq格式
使用fasterq
