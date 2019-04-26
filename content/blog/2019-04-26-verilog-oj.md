---
title: 一个项目的梳理Verilog_OJ
author: Dashjay
date: '2019-04-26'
slug: verilog-oj
categories:
  - 项目
tags:
  - 全栈
description: ''
featured: ''
featuredalt: ''
featuredpath: ''
linktitle: ''
type: post
---

# 1. 项目诞生 (2018 12 13)

何老师发了几个链接，然后我们就开始设计这个网站了
```
https://opencores.org/howto/eda
https://www.edaplayground.com/x/B
http://www.techep.csi.cuny.edu/~zhangs/v.html
https://github.com/timyang2010/VerilogOnlineJudge
```

## 第一周的计划让我们激动
<img src="/blog/2019-04-26-verilog-oj_files/1281556288571_.pic.jpg" alt="" width="99%"/>

## 雪松学长的加入
<img src="/blog/2019-04-26-verilog-oj_files/IMG_1D122DC93211-1.jpeg" alt="" width="49%"/>

## 开会的时候鲁一洋做的记录
<img src="/blog/2019-04-26-verilog-oj_files/屏幕快照 2019-04-26 下午10.28.13.png" alt=" 鲁一洋做的会议记录" width="59%"/>

## 需求文档0.2哦
[需求文档下载链接](/blog/2019-04-26-verilog-oj_files/need0.2.docx)
<img src="/blog/2019-04-26-verilog-oj_files/屏幕快照 2019-04-26 下午10.33.26.png" alt="" width="99%"/>

## 1-10开会整理
[1-10开会整理](/blog/2019-04-26-verilog-oj_files/meet1.10.docx)
<img src="/blog/2019-04-26-verilog-oj_files/屏幕快照 2019-04-26 下午10.36.22.png" alt="" width="99%"/>

----

3-22我们创建并且使用了Teambition

----

遇到了多伦多大学网站

----

国防科技大学网站

----

...我没有每天写日记的习惯，这次项目让我成长了不少，但是也让我感受到了心有余而力不足的感觉,项目开发和版本迭代并没有想象中的那么容易，那么干净利落，要准备的东西太多了。

> 我现在开始整理并且把制作这个项目的过程做成册来记录我的成长过程

1.项目初期开发使用PHP_Laravel一个简单干净的框架，当初为了把Vue嵌入进Laravel也花了不少时间那还是第一个版本（现在代码都不知道放在哪里了，非常难受）

2.项目第二版本是当我准备去参加计算机设计大赛的时候，重新对整个项目重构，还是使用了PHP_Laravel + vue来实现，数据库我都没换，但是我换了一个前端框架，之前使用的Element-UI被我换成了额Iview，我自己感觉重构了一个版本，但是其实并没有实质内容的变化，只不过后台调用了Verilog而已。

3.第三个版本是为了市赛准备的版本，数据库换成了额MongoDB，纯Docker化部署，PHP为核心，代码已经非常成熟了，然后使用Flask(python)给后台提供了便捷的评测API,只要文件储存的路径对了就可以了。


4.第四个版本是未来的版本，推测这个项目只会有五个版本，那么作为第倒数第二个版本，基础逻辑（除了评测之外的逻辑）使用PHP开发，数据库使用MongoDB，然后在评测部分使用FLask来编程，整个项目Docker化部署。以上说的是OJ这边，除此之外，在线模板开发的这个项目可以搞起来。

> 根据老师的设想 案例：电梯： 状态机 -> 代码编写 -> 在线板级验证

总共网站要集成这几个功能，第一个是画状态机。
<img src="/blog/2019-04-26-verilog-oj_files/3911556285971_.pic_hd.jpg" alt="" width="60%"/>

第二个是代码编写：
<img src="/blog/2019-04-26-verilog-oj_files/4221556287465_.pic_hd.jpg" alt="" width="99%"/>

第三个上板验证还是一块蓝图：
<img src="/blog/2019-04-26-verilog-oj_files/屏幕快照 2019-04-26 下午10.55.20.png" alt="" width="100%"/>

5.版本不设计，只对代码进行逻辑的链接，（设想）。