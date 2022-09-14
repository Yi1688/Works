---
title: 使用Unity开发Pico的基本设置
date: 2022-09-05 21:00:32
tags: 
- 导航
- Pico
- Unity
categories: Unity
---

# 下载Pico Unity XR 包并导入

<!--more-->

```bash
1、从Pico开发者官网下载Unity XR包，下载后解压。
2、Unity导入解压好Unity XR包中的json后缀文件
3、App ID: 填0（或者自己在Pico官网中注册开发者获得APP ID）
4、生成平台改为安卓
5、Project Settings -> XR Plug-in Management -> 安卓图标下勾选 PicoXR
```
这个时候打包在Pico中发现会闪退（如无法正常打包请看下方项目设置），提示该应用未通过版权检查，这个时候我们需要在Pico设备中查看设备序列号

```bash
Pico界面 -> 设置 -> 通用 -> 设备序列号
记下你的设备序列号，点击Unity界面上方中的PXR_SDK打开Platform Settings
Platform Settings中添加Device SN 把你的设备序列号输入进去打包就好了
```

# ！！！注意事项

```
[>_>]:   切记把下面的看完再打包
```

# Project Settings(项目设置，配置好这里再打包)

## 确认Pico的安卓版本
```bash
Pico界面 -> 设置 -> 通用 -> Android版本 (机房的Pico neo3 pro 安卓版本是安卓10)
```
---
## 确认安卓版本后的Unity设置
### 切换项目安卓版本：
```bash
Project Settings -> Player -> Other Settings -> Identification -> Minimun API Level -> 选择对应的安卓版本（没选择正确手柄不会移动）
```
### 切换Configuration模块设置
```bash
Project Settings -> Player -> Other Settings -> Configuration -> Scripting Backend 中的Mono改为IL2CPP
```

### 如图所示（示例是安卓10）

<a href="https://sm.ms/image/huMsnYGpTKo6iNy" target="_blank"><img src="https://s2.loli.net/2022/09/05/huMsnYGpTKo6iNy.png" ></a>

```
[>_>]:   可以打包了
```
