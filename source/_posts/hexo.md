---
title: Hexo 部署阿里云备忘
date: 2021-6-10 12:00:00
categories: Web
tags:
- Hexo
- 阿里云
---

前期部署参考[《将Hexo部署到阿里云轻量服务器（保姆级教程）》](https://hjxlog.com/posts/20191130a1.html#6-%E6%9C%8D%E5%8A%A1%E5%99%A8%E9%83%A8%E7%BD%B2)

## 常用命令

```bash
$ hexo clean // 清除缓存
$ hexo s // 生成本地服务器
$ hexo d -g // 打包上传 
```

修改 `package.json`：

```javascript
"build": "hexo clean & hexo d -g"
```

直接部署命令：

```bash
$ npm run build
```

## 新建文章

```bash
hexo new [post] // post: 标题名
```

## 阅读更多

在 `.md` 文本内插入 `<!--more-->` 即可生效。

## Typora

使用 Typora 编辑 `.md` 文档书写博文，Hexo 的标题、时间、分类以及标签的写法如下。

```markdown
---
title: 标题
date: 1999-1-8 00:00:00
categories:
- test
tags:
- test
---
```
