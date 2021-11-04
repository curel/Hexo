---
title: source ~/.bash_profile
date: 2021-10-25 10:46:56
categories: Web
tags: Mac
---

## 问题

每次打开终端都要先执行 `$source ~/.bash_profile `后才能正常使用`npm`。

## 解决方法

打开终端后编辑文件`.zshrc`。

```bash
vi ~/.zshrc
```

按`i`进入编辑模式添加：

```bash
source ~/.bash_profile
```

按`Esc`后输入`:wq`回车保存退出。

