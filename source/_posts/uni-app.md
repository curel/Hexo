---
title: uni-app 踩坑心路历程
date: 2021-11-23 12:30:00
categories: Web
tags: uni-app
---

拧螺丝日常。


## uni-app 引入 iconfont 编译失败

使用绝对路径：

```css
@font-face {
  font-family: "iconfont"; /* Project id  */
  src: url('./static/iconfont/iconfont.ttf') format('truetype');
}
```

## 生成二维码

[uQRCode 二维码生成插件 - DCloud 插件市场](https://ext.dcloud.net.cn/plugin?id=1287)

在 `template` 中创建 `<canvas/>` 并设置 `id`，画布宽高

```html
<canvas id="qrcode" canvas-id="qrcode" style="width: 354px;height: 354px;" />
```

<!--more-->

在 `script` 中引用js文件并调用生成方法

```javascript
import uQRCode from '@/components/uqrcode/common/uqrcode.js'

export default {
  onReady() {
    uQRCode.make({
        canvasId: 'qrcode',
        componentInstance: this,
        size: 354,
        margin: 10,
        text: 'uQRCode',
        backgroundColor: '#ffffff',
        foregroundColor: '#ff0000',
        fileType: 'png',
        errorCorrectLevel: uQRCode.errorCorrectLevel.H
    })
    .then(res => {
        console.log(res)
    })
  }
}
```

### 使用建议

如需在进入页面时生成二维码，建议使用`onReady`，不推荐在`onLoad`中生成。

关于高级使用：canvas在二维码生成中请当做一个生成工具来看待，它的作用仅是绘制出二维码。应把生成回调得到的资源保存并使用，显示用image图片组件，原因是方便操作，例如调整大小，或是H5端长按保存或识别，所以canvas应将它放在看不见的地方。不能用`display:none;overflow:hidden;`隐藏，否则生成空白。这里推荐canvas的隐藏样式代码

```html
<style>
    .canvas-hide {
        position: fixed;
        right: 100vw;
        bottom: 100vh;
        z-index: -9999;
        opacity: 0;
    }
</style>
```
## Eachers相关

### uni-app 引入

[uni-app引用echarts_梦寻汝的博客-CSDN博客](https://blog.csdn.net/weixin_42120669/article/details/106123645)

### 官方配置项文档

[Documentation - Apache ECharts](https://echarts.apache.org/zh/option.html#title)

> tip: 合理使用试一试。

### 提示框自定义配置

`option`  内设置 `tooltip` 的 `formatter`

```javascript
formatter: function(params, ticket, callback) {
	// console.log(params, ticket, callback)
	return res;
}
```

### 自定义提示框无法使用 br 标签

使用 `\n` 代替可实现换行，原因未知，html标签都不能使用。

## 兼容性相关

### IOS new Date()

IOS中 new Date中指定的字符串，无法使用 `-`

```javascript
new Date("2018-04-27 11:11") // null
```

必须使用 `/`

```javascript
new Date("2018/04/27 11:11") // ok
```

### 字体选择

```css
font-family: -apple-system, BlinkMacSystemFont, "PingFang SC", "Helvetica Neue", STHeiti, "Microsoft Yahei", Tahoma, Simsun, sans-serif;
```

## 样式相关

### 覆盖默认样式

使用 `/deep/` 深度选择器搭配 `!important` 在父选择器下覆盖子选择器，譬如：

```css
.list /deep/ .uni-checkbox-input {
	width: 24rpx !important;
	height: 24rpx !important;
}
```

### H5 和 App 端自定义导航栏

H5 部分，先在 `pages.json` 去除默认的导航栏：

```json
"style": {
	"navigationStyle": "custom",
	"navigationBarTextStyle": "white"
}
```

H5 配置自定义导航栏，可以用 [uView](https://www.uviewui.com/components/navbar.html) 的，功能按钮可以直接使用 slot 来做：

```html
<template>
	<view>
		<u-navbar title="首页">
            <view slot="left">
				......
			</view>
            <view slot="right">
				......
			</view>
		</u-navbar>
		<view class="content">
			<!-- 正文内容 -->
		</view>
	</view>
</template>
```

接着再单独配置 App 端的导航栏，譬如：

```json
"app-plus": {
	"titleNView": {
		"titleText": "地图",
		"backgroundImage": "linear-gradient(to left, rgb(28, 187, 180), rgb(150, 198, 135))",
	}
}
```

完整例子：

```json
"style": {
	"navigationStyle": "custom",
	"navigationBarTextStyle": "white",
	"titleNView": {
		"titleText": "地图",
		"backgroundImage": "linear-gradient(to left, rgb(28, 187, 180), rgb(150, 198, 135))",
	}
}
```

