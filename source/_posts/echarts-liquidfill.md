---
title: 在 Echarts 中绘制水球图
date: 2021-10-29 16:56:23
categories: Web
tags: Echarts
---

Liquid Fill 是一个基于 Echats 的插件，使用它可以绘制出水球图。

## 引入

```html
<script src='echarts.js'></script>  // 必须得使用Echarts
<script src='echarts-liquidfill.js'></script>
```

## 使用 npm 安装

```bash
$ npm install echarts
$ npm install echarts-liquidfill
```

引入：

```javascript
import * as echarts from 'echarts';
import 'echarts-liquidfill'
```
<!--more-->

## 例子

### 最基本的设置

将`type`设置为`'liquidFill'`：

```javascript
var option = {
    series: [{
        type: 'liquidFill',
        data: [0.6]
    }]
};
```

### 创建多个波浪

在`data`中添加更多数据：

```javascript
var option = {
    series: [{
        type: 'liquidFill',
        data: [0.6, 0.5, 0.4, 0.3]
    }]
};
```

## API

默认的配置：

```javascript
{
    data: [],

    color: ['#294D99', '#156ACF', '#1598ED', '#45BDFF'],
    center: ['50%', '50%'],
    radius: '50%',
    amplitude: '8%',
    waveLength: '80%',
    phase: 'auto',
    period: 'auto',
    direction: 'right',
    shape: 'circle',

    waveAnimation: true,
    animationEasing: 'linear',
    animationEasingUpdate: 'linear',
    animationDuration: 2000,
    animationDurationUpdate: 1000,

    outline: {
        show: true,
        borderDistance: 8,
        itemStyle: {
            color: 'none',
            borderColor: '#294D99',
            borderWidth: 8,
            shadowBlur: 20,
            shadowColor: 'rgba(0, 0, 0, 0.25)'
        }
    },

    backgroundStyle: {
        color: '#E3F7FF'
    },

    itemStyle: {
        opacity: 0.95,
        shadowBlur: 50,
        shadowColor: 'rgba(0, 0, 0, 0.4)'
    },

    label: {
        show: true,
        color: '#294D99',
        insideColor: '#fff',
        fontSize: 50,
        fontWeight: 'bold',

        align: 'center',
        baseline: 'middle'
        position: 'inside'
    },

    emphasis: {
        itemStyle: {
            opacity: 0.8
        }
    }
}

```

## 官方文档

项目地址：[echarts-liquidfill](https://github.com/ecomfe/echarts-liquidfill)
