---
title: 在Doprax上免费部署Xray节点-支持V2ray Trojan Shadowsocks
date: 2023-01-25 16:08:53
tags:
	- Doprax
	- xray
	- v2ray
	- vless
	- vmess
	- trojan
	- Shadowsocks
	- vpn

categories: 技术教程
---
![](https://img.baxx.eu.org/202301272114713.png)
Doprax是一家云提供商，它使网站和Web应用程序的部署和托管变得简单。只要把你的代码上传到GitHub，其余的将由Doprax完成。您可以将任何类型的网站和web应用程序部署到Doprax。从简单的hello世界到复杂的web应用程序。Doprax提供了数据库、搜索引擎和缓存等多种服务
<!--more-->
## 注册
https://www.doprax.com/signup/
![](https://img.baxx.eu.org/202301272038715.png)

## 新建应用
点击New App
![](https://img.baxx.eu.org/202301272043309.png)

App Title可以随便写
![](https://img.baxx.eu.org/202301272041154.png)

点击Create app
点进你刚刚创建的应用
![](https://img.baxx.eu.org/202301272045362.png)
![](https://img.baxx.eu.org/202301272047340.png)
点击Insert from app market
![](https://img.baxx.eu.org/202301272049901.png)
找到xray-for-paas，点击Insert
![](https://img.baxx.eu.org/202301272050364.png)
点击Add environment variable，添加相应的环境变量
项目可用到的变量:
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
  
  
  如：
  ![](https://img.baxx.eu.org/202301272052991.png)
  点击Deploy，然后点击蓝色箭头
  ![](https://img.baxx.eu.org/202301272055646.png)
  部署成功！
  ![](https://img.baxx.eu.org/202301272058721.png)
  
  项目地址:
  https://github.com/Misaka-blog/xray-for-paas
