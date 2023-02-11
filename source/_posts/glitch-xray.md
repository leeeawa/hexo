---
title: 在Glitch上部署Xray节点
date: 2023-02-09 12:06:59
tags:
	- Glitch
	- xray
	- vpn
	- v2ray
  	- trojan
  	- ss
categories: 免费资源
---
在Glitch上部署Xray节点
<!--more-->
## 准备材料
一枚邮箱（最好是大厂邮箱）
注意事项
文章仅供学习交流，请勿滥用此服务

## 部署步骤
1.打开项目地址：https://github.com/Misaka-blog/xray-for-glitch

2.点击“Code”→“Download ZIP”，下载压缩包
![](https://img.baxx.eu.org/202302112147117.png)


### 老项目
打开Releases，需要部署哪个协议就下载哪个协议的zip压缩包
![](https://img.baxx.eu.org/202302112147098.png)


3.编辑```config.json```文件，修改第17行（新项目为14行）的UUID（如为老项目的SS、Trojan协议则为密码）。【仅限新项目：如需修改ws路径请选中协议的路径，使用Ctrl+H进行替换】
![](https://img.baxx.eu.org/202302112148474.png)

{% note info %}UUID在线生成：https://www.uuidgenerator.net/{% endnote %}

4.（可选）如使用哪吒探针监控，则编辑```server.js```中第42行，修改域名、端口号及通信密钥
![](https://img.baxx.eu.org/202302112148972.png)

### 对于老项目
（可选）如需修改ws路径，则使用记事本或其他同类型的软件查找并替换api即可
![](https://img.baxx.eu.org/202302112152979.png)


5.打开Glitch官网：https://glitch.com/
6.点击“Sign up”按钮注册，如有账户点击“Login”登录
![](https://img.baxx.eu.org/202302112153147.png)

7.按照图示创建项目
![](https://img.baxx.eu.org/202302112154827.png)

8.在编辑器中，按照图示操作删除原本存在的文件
![](https://img.baxx.eu.org/202302112154245.png)

9.拖拽文件上传至Glitch文件编辑器
![](https://img.baxx.eu.org/202302112155721.png)

10.复制Live Site的链接，备用
![](https://img.baxx.eu.org/202302112155080.png)

11.修改105行的代码保活地址，然后访问伪装站。当伪装站出现“Hello world”即为成功
![](https://img.baxx.eu.org/202302112156378.png)

12.节点配置如下：
新项目：
```
协议：Vmess / Vless / Trojan / Shadowsocks
地址：appname.glitch.me
端口：443
UUID/密码：设置的UUID
额外ID：0
Shadowsocks加密方式：chacha20-ietf-poly1305
传输协议：ws
伪装域名：appname.glitch.me
路径：/协议名 或自己设置的路径
传输安全：TLS
跳过证书验证：true或false都可以
```
旧项目：
```
协议：Vmess / Vless / Trojan / Shadowsocks
地址：appname.glitch.me
端口：443
UUID/密码：设置的UUID/密码
额外ID：0
Shadowsocks加密方式：chacha20-ietf-poly1305
传输协议：ws
伪装域名：appname.glitch.me
路径：/api 或自己设置的路径
传输安全：TLS
跳过证书验证：true或false都可以
```
{% note info %}Xray内核支持WebSocket的0RTT降低延迟功能，可在path路径末尾加上参数：?ed=2048，以激活该功能{% endnote %}

{% note info %}由于Glitch暂时不支持自定义域名，如遇域名被墙可使用cf wkr/pages反代{% endnote %}

转载自 https://blog.misaka.rest/2023/01/16/glitch-xray/
