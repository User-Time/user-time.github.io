---
title: MicroPython ESP32 —— 开发环境配置
abbrlink: a6c631f8
date: 2024-09-01 20:31:15
tags:
  - 开发
  - MicroPython
  - ESP32
  - 物联网
  - Python
  - 教程
description: MicroPython开发环境配置，使用ESP32官方工具烧录固件，配置MicroPython开发环境，注意：实现通电自启后，下次连接设备调试时，需要先点停止按钮再点运行or同步
cover: https://s1.imagehub.cc/images/2024/09/09/632ab8560372d588e713ee62d9262431.md.jpg
---

## 一. 使用 ESP32 官方工具烧录固件

### 1. 下载 Flash 工具

[https://www.espressif.com/zh-hans/support/download/other-tools](https://www.espressif.com/zh-hans/support/download/other-tools) [![image](https://s1.imagehub.cc/images/2024/09/02/7f1761d062fbba8d4b4b3537a9f800b4.md.png)](https://www.imagehub.cc/image/image.buNyfj)

### 2. 下载 micropython 的 esp32 固件

[https://www.micropython.org/download/ESP32_GENERIC/](https://www.micropython.org/download/ESP32_GENERIC/) [![image](https://s1.imagehub.cc/images/2024/09/02/b885991d594ed3b60cd5a059449e1a1e.md.png)](https://www.imagehub.cc/image/image.buNiTz)

### 3. 将固件烧入 flash 中

- 先将下载的 Flash 工具解压缩，双击打开**flash_download_tool_3.9.7.exe** 选择板子型号： [![image](https://s1.imagehub.cc/images/2024/09/02/b9856857cf7e20df92d3813cc0e1f0b6.png)](https://www.imagehub.cc/image/image.buNLtg)
- 点击 ok 之后，需要配置 4 个地方：
- bin 文件路径
- 路径后面填写 0x1000
- 在左下角选择连接 MicroPython 的 COM 串口 _不知道哪个 com 口是开发板可以右键此电脑，点击管理找到设备管理器_ [![image](https://s1.imagehub.cc/images/2024/09/08/3753e937f45ebcbf63e45b42906a3eb6.md.png)](https://www.imagehub.cc/image/image.b9mA5e)
- 将 BAUD 调整为 115200 或 921600 `BAUD 是指波特率，也就是数据传输速率, 波特率越高，传输速度越快，但也越容易传输过程中产生错误数据`

[![image](https://s1.imagehub.cc/images/2024/09/02/f6d1af044a83529eea89f733c50a8e21.png)](https://www.imagehub.cc/image/image.buNQLo)

- 随后点击 ERASE 格式化开发板 [![image](https://s1.imagehub.cc/images/2024/09/08/850b4d64136cf1dda573475aec9d5491.png)](https://www.imagehub.cc/image/image.b9ZnUq)
- 显示完成之后再点击 Start 下载 Flash 并刷入开发板 [![image](https://s1.imagehub.cc/images/2024/09/08/311d2ba9b806b4a33a6f0eb32b67042d.png)](https://www.imagehub.cc/image/image.b9ZOe0) 点击 Strat 后显示： [![image](https://s1.imagehub.cc/images/2024/09/08/26b1d231adca6cd73db143d8a91985e7.png)](https://www.imagehub.cc/image/image.b9ZWsz)
- 状态变蓝之后则就是刷入完成了

## 二、安装开发环境

### 1. 下载 VSCode

[点击打开官网](https://code.visualstudio.com/ "点击下载 VSCode")

### 2. 配置环境

- 点击拓展 [![image](https://s1.imagehub.cc/images/2024/09/08/e4925ed20701f87e8f51036ae5e7f6ff.png)](https://www.imagehub.cc/image/image.b9ZPSb)
- 搜索 Chinese [![image](https://s1.imagehub.cc/images/2024/09/08/0a8b81b508c896cadc5a5fe705da7eb1.md.png)](https://www.imagehub.cc/image/image.b9ZKpA) 点击 **install** 进行安装，安装完成后会在 **VSCode** 的右下角显示下面这个弹窗，点击右下角的按钮重启 **VSCode** 客户端 _（就可以显示中文了）_ [![image](https://s1.imagehub.cc/images/2024/09/08/6446736fc886fad43048bdb57e445c28.png)](https://www.imagehub.cc/image/image.b9Zibk)
- 重启完后点击拓展，搜索 `RT-Thread MicroPython` [![image](https://s1.imagehub.cc/images/2024/09/08/2338bd638cb16d5153da0b3332746a17.md.png)](https://www.imagehub.cc/image/image.b9Zv7s) 点击 **安装** 后,安装成功后左下角会显示 5 个按钮，分别对应：
  - 创建工程
  - 连接设备
  - 同步文件
  - 运行代码
  - 终止运行

[![image](https://s1.imagehub.cc/images/2024/09/08/6b15fcca9948d0e88538af188fd357e8.png)](https://www.imagehub.cc/image/image.b9Z7kB)

## 三、最终测试

### 1. 首先接入 MicroPython

点击 RT-Thread 的第二个按钮，进行连接开发板 [![image](https://s1.imagehub.cc/images/2024/09/08/c6efd19d283ad8233d6896db1f7b9493.png)](https://www.imagehub.cc/image/image.b9m5LJ) [![image](https://s1.imagehub.cc/images/2024/09/08/6f1aaa9745ab06c079447e5aed78e20f.md.png)](https://www.imagehub.cc/image/image.b9mYJs)

接入成功后 VSCode 下方应该会显示如下截图： [![image](https://s1.imagehub.cc/images/2024/09/08/1de47fe6efcc544b15601b0389ac7cf0.md.png)](https://www.imagehub.cc/image/image.b9z1RG) _（如果只显示 cli.exe -p COM8 repl 没出现 >>> 可以稍等一会）_

### 2. 创建文件命名为 main.py

写入以下内容

```python
from machine import Pin
import time

led  = Pin(22, Pin.OUT) # 具体id看自己的板子
while True: # 无限循环
    for i in range(4): # 闪烁两次
        led.value(not led.value())
        time.sleep(0.25)
time.sleep(5)
```

### 3. 测试代码是否正常运行

点击第四个按钮，此时开发板应会每隔 5 秒闪烁 2 次

[![image](https://s1.imagehub.cc/images/2024/09/08/a17449f209718f0f9b6e03079620d584.png)](https://www.imagehub.cc/image/image.b9zgLS)

随后点击运行右边的停止 [![image](https://s1.imagehub.cc/images/2024/09/08/f93760a338ab844843656466dc7a6bfd.png)](https://www.imagehub.cc/image/image.b9zw5L) 然后进行文件同步 [![image](https://s1.imagehub.cc/images/2024/09/08/18f73337040239e271e1f9889cc4cb4b.png)](https://www.imagehub.cc/image/image.b9zl6B) [![image](https://s1.imagehub.cc/images/2024/09/08/7ab28d8d4feb166454552279319477e1.md.png)](https://www.imagehub.cc/image/image.b9z0Jq)

### 4. 设置为通电自启

> !!! 注意：实现通电自启后，下次连接设备调试时，需要先点停止按钮再点运行 or 同步

新建一个名为 **boot.py** 的文件，在文件内输入

```python
import main
```

_(import 之前新建的文件名)_

[![image](https://s1.imagehub.cc/images/2024/09/08/7eb3c020f68a7192762fa159e3f7827f.png)](https://www.imagehub.cc/image/image.b9z3mU) 然后进行同步，就完成通电自启了
