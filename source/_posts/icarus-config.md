---
title: Icarus 配置
date: 2021-11-05 08:59:37
categories: Web
tags:
- Hexo
- Icarus
---

记录配置 Icarus 的一些过程。

## KeyWords

在查看收录的时候发现 Icarus 似乎默认的配置项里并不包含关键字，导致 Blog 一个月了都没有被收录。

###  设置方法

编辑 `_config.icarus.yml` 里的 `meta` 项，注释里注明了写法：

```javascript
name=theme-color;content=#123456 => <meta name="theme-color" content="#123456">
```

那么只要按格式配置就可以，譬如：

```javascript
name=keywords;content=一穷,二白,三省
```
<!--more-->
## Valine

[Valine](https://valine.js.org/) 诞生于2017年8月7日，是一款基于LeanCloud的快速、简洁且高效的无后端评论系统。

### 获取 APP ID 和 APP Key

首先使用 Valine 需要先注册 LeanCloud，具体操作可以参考[官方文档](https://valine.js.org/quickstart.html)。

注册完后，就可以在应用内的「应用凭证」页面获取到 `AppID` 和 `AppKey` 了。

需要注意的是，记得配置安全域名，如果出现 `Code 403`，可能是因为域名没有备案的原因。

### iCarus 配置

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

具体的配置可以查看官方的[配置项](https://valine.js.org/configuration.html)。

### 数据管理

在 LeanCloud 内进入相关的应用，打开「数据存储」-「结构化数据」。

选择 `Comment` 项，就可以对留言的数据进行操作。

## Icon

Icarus 使用的是 [Font Awesome](https://fontawesome.com/v5.15/icons?d=gallery&p=5&m=free) v5.15 版本。

### 使用方法

和 icon-font 一样，在网站上查询相关的类名插入即可。

```Html
<i class="fab fa-fish"></i>
```

## RSS

首先 npm 安装插件。

```bash
$ npm install hexo-generator-feed
```

接着在根目录下的 `_config.yml` 添加以下代码：

```javascript
Plugins: 
- hexo-generate-feed
```

最后在 `_config.icarus.yml` 内查找 `rss` 字段，并填入地址：

```javascript
rss: /atom.xml
```
