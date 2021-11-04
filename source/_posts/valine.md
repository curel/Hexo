---
title: Icarus 配置 Valine 评论
date: 2021-11-03 10:28:16
categories: Web
tags:
- Hexo
- Icarus
---

[Valine](https://valine.js.org/) 诞生于2017年8月7日，是一款基于LeanCloud的快速、简洁且高效的无后端评论系统。

## 获取 APP ID 和 APP Key

首先使用 Valine 需要先注册 LeanCloud，具体操作可以参考[官方文档](https://valine.js.org/quickstart.html)。

注册完后，就可以在应用内的「应用凭证」页面获取到 `AppID` 和 `AppKey` 了。

需要注意的是，记得配置安全域名，如果出现 `Code 403`，可能是因为域名没有备案的原因。

## iCarus 配置

打开主题目录类的配置文件，`./icarus/_config.yml`。

对 `commit` 部分进行配置：

```javascript
comment:
    type: valine
    app_id: xxx
    app_key: xxx
    placeholder: ""
    notify: false
    verify: false
    avatar:
    avatar_force: false
    meta: ["nick", "mail", "link"]
    page_size: 10
    visitor: false
    highlight: true
    record_ip: true
```
<!--more-->
具体的配置可以查看官方的[配置项](https://valine.js.org/configuration.html)。

## 数据管理

在 LeanCloud 内进入相关的应用，打开「数据存储」-「结构化数据」。

选择 `Comment` 项，就可以对留言的数据进行操作。
