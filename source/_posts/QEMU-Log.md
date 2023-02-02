---
title: QEMU新建空白镜像与启动的命令
date: 2022-10-15 12:06:59
tags:
	- QEMU
	- QEMU新建空白镜像
	- QEMU启动
	- QEMU命令
categories: 技术教程
---
QEMU是一个通用的开源机器和用户空间仿真器和虚拟机。
<!--more-->
# 新建空白镜像
```
qemu-img create -f qcow2 /root/w.qcow2 5G
```
# 启动
```
qemu-system-x86_64 -m 512 -boot c -hda /root/windowsxp.qcow2 -net nic,model=rtl8139 -net user -soundhw ac97 -vga cirrus -vnc :1 -net user,hostfwd=tcp::3389-:3389 -localtime
```
