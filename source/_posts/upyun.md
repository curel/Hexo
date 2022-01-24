---
title: 又拍云 + PicGo 搭建图床
date: 2021-12-06 18:00:00
categories: Web
tags:
- 又拍云
- PicGo
- 图床
---

之前在废话胶囊插入图片都是再用 ImgURL 这个免费图床，但显然免费的图床载入速度不是很理想。

于是就着手考虑使用又拍云 + PicGo 的组合来存储和使用博客还有废话胶囊的图片。

并且各家的云存储都可以薅到免费的空间，譬如这次使用的又拍云。

在加入又拍云联盟后每个月可以免费使用 10GB 存储空间以及 15GB 流量，对于普通的个人博客，这个大小是肯定足够使用的，而代价就是要在页尾放上又拍云的跳转链接 Logo。<!--more-->

那么不多哔哔，开始食用说明。

注册账号之类的就不详述了。


### 创建云存储

1. 授权方式可以选择暂不授权，之后再创建操作员。

![](http://i.becure.cn/img202112091715392.png)

2. 绑定一个加速域名。

![](http://i.becure.cn/img202112091717196.png)

3. 复制对应的 `CNAME` 地址。

![](https://i.becure.cn/img20211206145200.png)

4. 前往域名控制台添加 `CNAME` 记录。

![](https://i.becure.cn/img20211206145615.png)

5. 创建操作员并授权。

![](https://i.becure.cn/img20211206145904.png)

![](https://i.becure.cn/img20211206150038.png)

### PicGo 配置

接着就是进行 PicGo 的配置。

首先得去 Github 将 PicGo 的安装包下载下来，[PicGo 2.30](https://github.com/Molunerfinn/PicGo/releases/tag/v2.3.0)。

在「图床设置」中选择「又拍云图床」，完成相关的配置就结束了。

![](https://i.becure.cn/img20211206152454.png)

![](https://i.becure.cn/img20211208083951.png)
