---
title: Dnsflare - 可视化地修改Cloudflare域名的DNS记录
date: 2023-01-27 12:06:59
tags:
	- cfp
	- cloudflarepartner
	- dnsflare
	- Cloudflare
	- CloudflareDNS
	- Cloudflare修改DNS
	- CloudflarePro
categories: 软件资源
---
![](https://img.baxx.eu.org/202301272228410.png)
Dnsflare - 可视化地修改Cloudflare域名的DNS记录
<!--more-->
# Dnsflare

可视化地修改Cloudflare域名的DNS记录

项目地址：
https://github.com/5aaee9/Dnsflare/
演示:
https://cf.baxx.eu.org/
https://dnsflare-indexyz.vercel.app/

## 原因
Cloudflare 非常鸡贼的 ban 掉了 `externallyManaged` 用户访问 Cloudflare 控制台编辑 DNS Record 的功能, 然后有些 Partner 又已经跑了 ~~不是~~, 但是又眼馋 pro

### 优点
所有请求由本地浏览器产生, 服务端仅进行 CORS 处理

Partner 无法直接添加 A 记录 (据说), 而且 Partner API 在开启 2FA 的情况下无法使用

## 使用
到 [Cloudflare 的 API Token 设定](https://dash.cloudflare.com/profile/api-tokens) 中新建一个 Token, 给这个 Token 以下权限

- Zone.DNS 写权限 (用于写入 DNS 记录)
- Zone.Zone 读权限 (用于读取域名列表)

- Zone.SSL and Certificates 读写权限 (用于展示和修改 SSL 证书供应商)

然后访问 [演示](https://dnsflare-indexyz.vercel.app) 来登录到面板
## 部署

### 部署到 Vercel
点击以下按钮将 Dnsflare 一键部署到 Vercel

[![一键部署到Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/5aaee9/Dnsflare/)

### 部署到 Cloudflare

安装 wrangler cli:

```
npm i -g wrangler
```

构建前端页面

```
yarn install
yarn run build
```

部署页面

```
wrangler pages publish dist
```

