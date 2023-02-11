---
title: 在Patr上部署Xray节点
date: 2023-01-15 12:06:59
tags:
	- Patr
	- xray
	- vpn
	- v2ray
	- trojan
	- ss
categories: 免费资源
---
在Patr上部署Xray节点
<!--more-->
## 准备材料
一枚邮箱（最好是大厂邮箱）
## 注意事项
文章仅供学习交流，请勿滥用此服务

## 部署步骤
1.打开Patr官网：https://patr.cloud/
2.点击“Try Patr for free”注册账号，如有账号请登录
![](https://img.baxx.eu.org/202302112224710.png)

3.输入全名、用户名，邮箱及密码
![](https://img.baxx.eu.org/202302112225954.png)

4.检查邮件验证码并输入上来
![](https://img.baxx.eu.org/202302112225015.png)

5.依次点击“Infrastructure”→“Deployments”，点击“Create deployment”按钮
![](https://img.baxx.eu.org/202302112225367.png)

6.输入项目名称（别提到v2、v2ray、xray等一些明显字眼），来源选Docker Hub，镜像名输入```misakablog/xray-for-paas```，tag输入```latest```，地区选新加坡（实测只有新加坡免费）
![](https://img.baxx.eu.org/202302112225086.png)

7.http端口输入80，填写环境变量。变量说明如下表格所示。其余默认即可
![](https://img.baxx.eu.org/202302112226489.png)

  | 变量名 | 是否必须 | 默认值 | 备注 |
  | ------------ | ------ | ------ | ------ |
  | UUID         | 否 | de04add9-5c68-8bab-950c-08cd5320df18 | 可在线生成 https://www.uuidgenerator.net/ |
  | VMESS_WSPATH | 否 | /vmess | 以 / 开头 |
  | VLESS_WSPATH | 否 | /vless | 以 / 开头 |
  | TROJAN_WSPATH | 否 | /trojan | 以 / 开头 |
  | SS_WSPATH | 否 | /shadowsocks | 以 / 开头 |
  | NEZHA_SERVER | 否 |        | 哪吒探针服务端的 IP 或域名 |
  | NEZHA_PORT   | 否 |        | 哪吒探针服务端的端口 |
  | NEZHA_KEY    | 否 |        | 哪吒探针客户端专用 Key |
 
8.按照下图配置
![](https://img.baxx.eu.org/202302112227284.png)

9.等待创建。待创建成功之后点击“Public URL”。（更新：近期Patr好像服务器炸了，如果一直出现deploying也可以不用管他，照样进去，伪装网站能正常打开即可）
![](https://img.baxx.eu.org/202302112227903.png)

10.复制粘贴这里提供的链接，备用
![](https://img.baxx.eu.org/202302112228276.png)

11.节点配置如下：
```
协议：Vmess / Vless / Trojan / Shadowsocks
地址：80-xxxxxx.patr.cloud
端口：443
UUID/密码：自动生成或设置的uuid变量内容
额外ID：0
Shadowsocks加密方式：chacha20-ietf-poly1305
传输协议：ws
伪装域名：80-xxxxxx.patr.cloud
路径：/vmess（/vless、/trojan、/shadowsocks）或设置的VMESS_WSPATH（VLESS_WSPATH、TROJAN_WSPATH、SS_WSPATH）变量内容
传输安全：TLS
跳过证书验证：true或false都可以
```
{% note info %}Xray内核支持WebSocket的0RTT降低延迟功能，可在path路径末尾加上参数：?ed=2048，以激活该功能{% endnote %}

{% note info %}由于Patr暂时不支持自定义域名，如遇域名被墙可使用cf wkr/pages反代{% endnote %}

转载自 https://blog.misaka.rest/2023/01/18/patr-xray/
