---
title: 使用Cloudflare Worker反向代理V2ray
date: 2023-01-31 12:06:59
tags:
	- CloudflareWorker
	- V2ray
	- 反向代理
  - 反代
	- Cloudflare
categories: 技术教程
---
![](https://img.baxx.eu.org/202301272256903.png)
使用Cloudflare Worker反向代理V2ray
<!--more-->
# 安装

代码
```
addEventListener(
  "fetch",event => {
     let url=new URL(event.request.url);
     url.hostname="www.example.com";
     let request=new Request(url,event.request);
     event. respondWith(
       fetch(request)
     )
  }
)
```
