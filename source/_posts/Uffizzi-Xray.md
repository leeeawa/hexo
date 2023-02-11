---
title: 在Uffizzi云平台上部署xray节点
date: 2023-02-08 12:06:59
tags:
	- Uffizzi
	- xray
	- vpn
	- v2ray
  	- trojan
  	- ss
categories: 免费资源
---
在Uffizzi云平台上部署xray节点
<!--more-->
## 准备材料
一枚GitHub账户
注意事项
文章仅供学习交流，请勿滥用此服务

## 部署步骤
1.打开GitHub项目：https://github.com/Misaka-blog/xray-for-uffizzi
2.点击“Use this template”按钮，创建一个新库
![](https://img.baxx.eu.org/202302112106084.png)

3.输入库的名称，然后选择私库，创建私库
![](https://img.baxx.eu.org/202302112107664.png)

4.在 entryport.sh 的 4-11 行修改项目变量
![](https://img.baxx.eu.org/202302112108372.png)

5.打开Uffizzi官网：https://www.uffizzi.com ，点击“Sign up”注册
![](https://img.baxx.eu.org/202302112109837.png)

6.使用GitHub登录，严重建议小号部署！
![](https://img.baxx.eu.org/202302112109037.png)

7.点击“Uffizzi CI”，再点击“Configure GitHub”
![](https://img.baxx.eu.org/202302112109107.png)

8.点击“Install & Authorize”
![](https://img.baxx.eu.org/202302112109659.png)

9.选择自己的xray私库，然后点击“Setup up project”
![](https://img.baxx.eu.org/202302112110226.png)

10.按照下图配置，compose文件名称为docker-compose.uffizzi.yml，然后保存
![](https://img.baxx.eu.org/202302112110640.png)

11.点击“Test Compose”
![](https://img.baxx.eu.org/202302112110522.png)

12.耐心等待3-5分钟，待下方的Status打勾的时候，即为成功。复制Preview URL备用
![](https://img.baxx.eu.org/202302112111838.png)

13.节点配置如下：
```
协议：Vmess / Vless / Trojan / Shadowsocks
地址：deployment-xxxxx-project-name-xxxx.app.uffizzi.com
端口：443
UUID/密码：自动生成或设置的uuid变量内容
额外ID：0
Shadowsocks加密方式：chacha20-ietf-poly1305
传输协议：ws
伪装域名：deployment-xxxxx-project-name-xxxx.app.uffizzi.com
路径：/vmess（/vless、/trojan、/shadowsocks）或设置的VMESS_WSPATH（VLESS_WSPATH、TROJAN_WSPATH、SS_WSPATH）变量内容
传输安全：TLS
跳过证书验证：true或false都可以
```

转载自 https://blog.misaka.rest/2023/02/05/uffizzi-xray/
