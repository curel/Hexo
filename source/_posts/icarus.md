---
title: Hexo 设置 Icarus 主题
date: 2021-10-23 08:41:47
categories: Web
tags:
- Hexo
- Icarus
---

记录一下配置 Icarus 这个主题的过程。

## 安装

终端 `cd` 进 hexo 的根目录。

```bash
$ npm install hexo-theme-icarus
$ hexo config theme icarus
```

还有种从源码安装的方法，可以参考官方文档 - [Icarus快速上手](https://ppoffice.github.io/hexo-theme-icarus/uncategorized/icarus%E5%BF%AB%E9%80%9F%E4%B8%8A%E6%89%8B/)

## 配置

编辑 `_config.icarus.yml` 进行配置。
<!--more-->
## 个人配置

### 修改 CDN

编辑 `_config.icarus.yml`，修改 `providers`：

```javascript
providers:
    # Name or URL template of the JavaScript and/or stylesheet CDN provider
    cdn: loli
    # Name or URL template of the webfont CDN provider
    fontcdn: loli
    # Name or URL of the fontawesome icon font CDN provider
    iconcdn: loli
```

### 去除文章更新时间

在  `themes/icarus/layout/common/article.jsx` 里找到 `Last Update Date` 注释掉以下部分：

```javascript
{shouldShowUpdated && <span class="level-item" dangerouslySetInnerHTML={{__html: _p('article.updated_at', `<time dateTime="${date_xml(page.updated)}" title="${new Date(page.updated).toLocaleString()}">${date(page.updated)}</time>`)}}></span>}
```

###  添加备案号

在 `themes/icarus/layout/common/footer.jsx` 里找到以下字段：

```javascript
<a href="https://github.com/ppoffice/hexo-theme-icarus" target="_blank" rel="noopener">Icarus</a>
```
在后面直接添加，譬如：

```javascript
<a href="https://github.com/ppoffice/hexo-theme-icarus" target="_blank" rel="noopener">Icarus</a>&nbsp;&nbsp;粤ICP备2021079776号
```

## 相关链接

[Github: hexo-theme-icarus](https://github.com/ppoffice/hexo-theme-icarus)
