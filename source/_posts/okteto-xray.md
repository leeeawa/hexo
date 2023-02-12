---
title: 在Okteto上搭建xray节点
date: 2023-02-09 12:06:59
tags:
	- Okteto
	- xray
	- vpn
	- v2ray
  - trojan
  - ss
categories: 免费资源
---
在Okteto上搭建xray节点
<!--more-->
## 准备材料
一枚GitHub账户，并绑定的非大厂企业邮箱
## 部署步骤
1.打开GitHub项目：https://github.com/Misaka-blog/xray-for-okteto
2.点击“Use this template”按钮，创建一个新库
![](https://img.baxx.eu.org/202302121300016.png)

3.输入库的名称，然后选择私库，创建私库
![](https://img.baxx.eu.org/202302121300235.png)

4.在 ```entryport.sh``` 的 4-11 行修改项目变量
![](https://img.baxx.eu.org/202302121300452.png)

5.在 ```docker-compose.yml``` 的第二行修改默认的服务名称，以避免连坐
![](https://img.baxx.eu.org/202302121301739.png)

6.打开Okteto的官网：https://cloud.okteto.com/ ，点击“Login with GitHub”登录
![](https://img.baxx.eu.org/202302121301637.png)

7.点击“Launch Dev Environment”
![](https://img.baxx.eu.org/202302121301314.png)

8.选择自己的私库，点击“Launch”按钮
![](https://img.baxx.eu.org/202302121301692.png)

9.等待3-5分钟后，Okteto云的节点就已经部署完成。复制EndPoint URL备用
![](https://img.baxx.eu.org/202302121302625.png)

10.节点配置如下：
```
协议：Vmess / Vless / Trojan / Shadowsocks
地址：servicename-namespace.cloud.okteto.net
端口：443
UUID/密码：自动生成或设置的uuid变量内容
额外ID：0
Shadowsocks加密方式：chacha20-ietf-poly1305
传输协议：ws
伪装域名：servicename-namespace.cloud.okteto.net
路径：/vmess（/vless、/trojan、/shadowsocks）或设置的VMESS_WSPATH（VLESS_WSPATH、TROJAN_WSPATH、SS_WSPATH）变量内容
传输安全：TLS
跳过证书验证：true或false都可以
```

转载自 https://blog.misaka.rest/2023/02/08/okteto-xray/
