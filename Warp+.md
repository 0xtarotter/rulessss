---
layout: '../../layouts/MarkdownPost.astro'
title: 'Surge新手捣鼓Warp+ '
pubDate: 2023-04-19
description: ''
author: 'Steve'
cover:
    url: 'https://user-images.githubusercontent.com/17553115/233017536-5855dc37-972b-4918-bfda-490a19e866e8.png'
    square: 'https://user-images.githubusercontent.com/17553115/233017536-5855dc37-972b-4918-bfda-490a19e866e8.png'
    alt: 'cover'
tags: ["Steve 分享", "Warp+", "Surge"]
theme: 'light'
featured: false
---

# 前言

此方法不仅仅适用于Surge，基本适用于支持 `wireguard协议`的代理软件。

## 获取 Warp+ 24PB流量

1. 打开链接Wrap+ Bot：[https://t.me/generatewarpplusbot](https://t.me/generatewarpplusbot) 
2. 去Telegram，按要求输入命令进行获取warp+ unlimited license key

## 通过 wgcf 获取配置

1. 安装 brew 之前有篇Blog介绍过。 点击： [传送门](https://blog.steveee.me/posts/Homebrew/)
2. 安装

```bash
brew install wgcf
```

```bash
wgcf register
```

```bash
open .
```

找到以下文件`wgcf-account.toml`



![wgcf-account.toml|inline](https://user-images.githubusercontent.com/17553115/233011720-53249899-939d-4df1-a300-3a7e807d12d0.png)



使用编辑器打开后，修改`wgcf-account.toml` 中的 `license_key` 后保存。



![修改wgcf-account.toml|inline](https://user-images.githubusercontent.com/17553115/233011743-edbfeebf-ed0e-4bb5-b8f8-f6c9d1145ffc.png)



## 更新 wgcf-account.toml 配置

保存好修改的配置文件后，记得更新一下，运行

```bash
wgcf update
```



## 生成配置文件

运行生成命令,同目录下会生成一个新的 `wgcf-profile.conf `文件

```bash
wgcf generate
```

运行以下命令打开目录

```bash
open .
```

打开 `wgcf-profile.conf `文件，将各项数据填入Surge中。



![填入Surge|inline](https://user-images.githubusercontent.com/17553115/233015208-394f3d5f-ffff-44be-9615-bd142e569a60.png)



## 测试



![Surge](https://user-images.githubusercontent.com/17553115/233016740-8fe556e6-c325-44bf-b3cd-5bce3dd98610.png)



![YouTube 4K 测试](https://user-images.githubusercontent.com/17553115/233016680-0b3a2412-2d08-4745-b038-6cee48f35655.png)



## 写在最后

如果你觉得麻烦，我也给你提供了一份懒人配置。按需使用。

```bash
[Interface]
PrivateKey = AOwZStw/z7kOrfdqvisaeltrb9sCf4MWsPH5D9/BBVI=
Address = 172.16.0.2/32
Address = 2606:4700:110:84fc:7d13:c45:f900:8f76/128
DNS = 1.1.1.1
MTU = 1280
[Peer]
PublicKey = bmXOC+F1FxEMF9dyiK2H5/1SUtzH0JuVo51h2wPfgyo=
AllowedIPs = 0.0.0.0/0
AllowedIPs = ::/0
Endpoint = engage.cloudflareclient.com:2408

```

