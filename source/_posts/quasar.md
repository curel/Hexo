---
title: Quasar 项目创建
date: 2021-10-08 12:00:00
categories: Web
tags: Quasar
---

换了新的技术栈，Vue2/Typescript/Quasar/Pug/Stylus，首先从Quasar这个UI框架开始踩起。

### 创建新的项目

在Windows下，修改用户的PATH环境变量。如果使用yarn，则添加`%LOCALAPPDATA%\yarn\bin`，否则，如果使用npm，则添加`%APPDATA%\npm`。

```bash
$ yarn global add @quasar/cli
# 或是
$ npm install -g @quasar/cli
```

使用Quasar CLI创建一个项目文件夹：

```bash
$ quasar create <folder_name> --branch v1
```
<!-- more -->
进行一些设置：

```bash
# 项目名称
?Project name (internal usage for dev) (quasar)

# 项目产品名称（如果构建移动应用程序必须以字母开头）
? Project product name (must start with letter if building mobile apps) (Quasar App)

# 项目描述
? Project description (A Quasar Framework app)

# 作者
? Author (Kiro)

# 选择使用的 CSS 预处理器
? Pick your favorite CSS preprocessor: (can be changed later) (Use arrow keys)
  Sass with SCSS syntax (recommended)
  Sass with indented syntax (recommended)
> Stylus (deprecated)
  None (the others will still be available)

# 选择 Quasar 组件和指令导入策略：（可以稍后更改）
? Pick a Quasar components & directives import strategy: (can be changed later)
> * Auto-import in-use Quasar components & directives
    - also treeshakes Quasar; minimum bundle size
  * Import everything from Quasar
    - not treeshaking Quasar; biggest bundle size
    
# 选择项目所需要的功能
? Check the features needed for your project:
 (*) ESLint (recommended)
 (*) TypeScript
 (*) Vuex
 (*) Axios
 ( ) Vue-i18n
>( ) IE11 support

# 选择组件风格
? Pick a component style:
  Composition API (recommended) (https://github.com/vuejs/composition-api)
> Class-based (recommended) (https://github.com/vuejs/vue-class-component & https://github.com/kaorun343/vue-property-decorator)
  Options API

# 选择一个 ESLint 预设
? Pick an ESLint preset:
  Prettier (https://github.com/prettier/prettier)
> Standard (https://github.com/standard/standard)
  Airbnb (https://github.com/airbnb/javascript)

# 项目创建好后继续安装项目依赖？
? Continue to install project dependencies after the project has been created? (recommended)
> Yes, use Yarn (recommended)
  Yes, use NPM
  No, I will handle that myself
```

在命令行中输入

```bash
# projectName 为项目目录名
cd <projectName>
# 跑起来
quasar dev
```

