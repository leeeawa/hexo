---
title: 在Deepnote上部署xray节点
date: 2023-02-08 12:08:59
tags:
	- Deepnote
	- xray
	- vpn
	- v2ray
  - trojan
  - ss
categories: 免费资源
---
在Deepnote上部署xray节点
<!--more-->
准备材料
一枚邮箱（最好是大厂邮箱）
部署步骤
1.打开Deepnote官网：https://deepnote.com/ ，点击“Get started”进行注册账户。如有账号点击“Sign in”进行登录
![](https://img.baxx.eu.org/202302121304598.png)

2.可以使用GitHub、Google和微软账户进行登录，也可以使用邮件注册并登录
![](https://img.baxx.eu.org/202302121304258.png)

3.按照图示创建项目
![](https://img.baxx.eu.org/202302121304560.png)

4.点击Environment中的Initialization，打开里面的```init.ipynb```。删除里面自带的代码块并创建一个，输入下面的内容。然后点击“Run notebook”
```!sleep infinity```
5.打开Allow Incoming Connections的开关，复制链接备用
![](https://img.baxx.eu.org/202302121306348.png)

6.点击“Terminal”，创建一个命令行
7.复制粘贴，并运行以下代码
```
wget -N https://raw.githubusercontent.com/Misaka-blog/xray-for-deepnote/main/deep.sh && bash deep.sh
```
8.输入UUID，UUID可在此生成：https://www.uuidgenerator.net/ 。也可以直接回车使用脚本自己的UUID
![](https://img.baxx.eu.org/202302121307031.png)

9.出现这个提示，打开第5步的链接，提示“Bad request”即为成功
![](https://img.baxx.eu.org/202302121307431.png)

10.节点配置如下：
```
协议：Vmess / Vless / Trojan / Shadowsocks
地址：xxxxx.deepnoteproject.com
端口：443
UUID/密码：8d4a8f5e-c2f7-4c1b-b8c0-f8f5a9b6c384 或自己定义的UUID
额外ID：0
Shadowsocks加密方式：chacha20-ietf-poly1305
传输协议：ws
伪装域名：xxxxx.deepnoteproject.com
路径：/vmess（/vless、/trojan、/shadowsocks）
传输安全：TLS
跳过证书验证：true或false都可以
```

转载自 https://blog.misaka.rest/2023/02/08/deepnote-xray/
