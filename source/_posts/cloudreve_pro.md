---
title: CloudrevePro捐赠版3.5.3源代码
date: 2023-01-28 5:02:23
tags:
	- cloudreve
	- cloudreve_pro
	- cloudreve捐赠版
	- cloudreve破解
	- cloudreve破解版
	- cloudreve源代码
categories: 软件资源
---
![](https://img.baxx.eu.org/202301280017984.png)
Cloudreve 可助你即刻构建出兼备自用或公用的网盘服务，通过多种存储策略的支持、虚拟文件系统等特性实现灵活的文件管理体验。
版本3.5.3，有源码，有编译好的文件，但是没有配套的授权文件；据分享文件的大佬说，只需要修改"app.go"文件就能跳过授权文件，可惜他没有教咋改，我记得底下评论有说删几行代码就行；我的GO语言也学的不好，看不出来哪行代码是要删的，留在我手里也没用，分享给各位
<!--more-->
## 仅供用户研究与学习GO语言使用，请在下载后24小时内删除，支持正版网盘系统！
附：
**根据二○○二年一月一日《计算机软件保护条例》规定：为了学习和研究软件内含的设计思想和原理，通过安装、显示、传输或者存储软件等方式使用软件的，可以不经软件著作权人许可，不向其支付报酬!**

原作者已经更新到3.6.2了，挺好一个网盘系统，但是授权太贵了，一些免费版也需要的功能（比如文件转存）也不下放，所以出此下策，希望各位不要捅出去，下完文件说个谢谢就行，回头要是能给我私发编译好的魔改版Cloudreve就更好了

有会GO语言的大佬也来看看，“app.go”文件到底哪几行代码要删

来自某大佬的指导：授权代码在backend-pro-master\bootstrap\app.go的InitApplication函数中，自行删除并重新编译就行了
目前也有大佬认为直接删除app.go的InitApplication函数不行，其中有三个关键变量；我比较认同这种说法
据最新反馈，前端也有验证，改完后端key授权验证还要改前端代码

## 下载
Cloudreve Pro 3.5.3 编译好的文件+源代码:
https://onedrive.baxx.eu.org/api/raw/?path=/Cloudreve/cloudreve_3.5.3.zip

Cloudreve Pro 3.2.0 编译好的文件+授权Key(无源代码):
https://onedrive.baxx.eu.org/api/raw/?path=/Cloudreve/cloudreve_3.2.0.zip

注意：授权key不是3.5.3版本，不能与Cloudreve 3.5.3版本一同使用

原项目地址:https://github.com/cloudreve/Cloudreve/

https://hostloc.com/thread-1129980-1-1.html
