---
title: Macbook M1 重置系统不完全指北
date: 2021-11-02 09:08:52
categories: Pit
tags: Mac
---

手上的 Macbook Air 在小黄鱼挂出去了，需要抹除数据重置系统。

系统退出了 Apple ID，设备里也移除了 MacBook。

扒贴看了一下，没备份，就直接把磁盘给抹除了。

之前好像直接抹除磁盘重装 Big Sur 会有一些坑，但升级到了 Monterey 后并没有遇到，也可能是我提前移除了 Apple ID 还有在 Cloud 里 移除设备的原因。
<!--more-->
## 步骤

以下是M1设备的步骤：

1. 将机器关机。

2. 长按电源键不松手，先会出现「**继续按住直到启动选项**」提示。

3. 不要松手，直到出现「**正在载入选项**」就可以松开了。

4. 在「磁盘」和「选项」中选择「**选项**」。

5. 选择内置的第一个磁盘，进行抹除，格式为APFS，官网步骤是「抹除卷宗」，但我直接进行了「抹除」。

6. 抹除完，右上角连接 Wifi 或者是给设备插上网线。

7. 直接选择重新安装「**macOS**」就完事了，这个过程大概一个小时左右。

## 注意

值得一提的是，过程电量 <= 50 在安装前会提示需要连接电源，避免水逆，最好还是插电操作，在抹除磁盘前，最好还是数据备份，万无一失。