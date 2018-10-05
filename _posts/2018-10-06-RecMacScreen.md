---
layout: post
title: 苹果Mac电脑录屏教程
date: 2018-10-06
categories: tech
tags: [Mac,录屏]
description: mac电脑录屏教程
---

### 这个教程能解决什么问题？

经常我们需要保存一些电脑正在播放的视频，本教程主要可以解决这样的应用场景

1. 电脑播放视频，录制屏幕和声音
2. 电脑播放视频，录制屏幕和声音，并且录制自己的声音(录制教学视频)

### 1. 软件准备

* 安装 [Soundflower](https://github.com/mattingalls/Soundflower/releases),Mac下的一个虚拟设备的软件
* mac自带的QuickTime Player  
* mac自带的Audio MIDI Setup
> Soundflower的安装和QuickTime Player的使用，这里就不详细说了，大家自行搜索

### 2. 基本的概念&软件设置

**概念**

Soundflower是MAC下虚拟设备的软件，它会虚拟出Soundflower(2ch)和Soundflower(64ch)两个虚拟声音设备。我们主要是用Soundflower(2ch)这个虚拟设备。  
Soundflower(2ch)大家可以理解为 它是一个输出和输入的双向声音设备，可以把声音播放到它，也可以从它获取声音。

**基本设置：**

##### 2.1. 配置多路输出设备

使用Mac自带的**Audio MIDI Setup**新增**Create Multi-Output Device**，勾选 Soundflower(2ch) 虚拟设备以及Build-in Output这两个选项  
这个设备表示：声音会同步输出的电脑的声音音响以及虚拟的2ch设备   
![多路输出]( {{ "/assert/20181006_1.jpg" | prepend: site.img_location }} )

##### 2.2. 配置合并输入设备

还是使用Mac自带的**Audio MIDI Setup**新增**Create Aggregate Device**，勾选 Soundflower(2ch) 虚拟设备以及Build-in MicroPhone这两个选项          
这个设备表示：会从 电脑的麦克风和虚拟的2ch设备 获取声音  
![合并输入]( {{ "/assert/20181006_2.jpg" | prepend: site.img_location }} ) 

### 3. 录屏教程

* 3.1 设置电脑的声音为 **Multi-output Device**(注意：请提前设置好音量大小，选择后将无法设置)

  ![合并输入]( {{ "/assert/20181006_3.jpg" | prepend: site.img_location }} ) 

* 3.2 打开Quick-Time Player，使用屏幕录制，设置声音输入为 **Soundflower(2ch)**       

  ![合并输入]( {{ "/assert/20181006_4.jpg" | prepend: site.img_location }} )     


### 4. 带自己声音的录屏

* 3.1 设置电脑的声音为 **Multi-output Device**(注意：请提前设置好音量大小，选择后将无法设置)

  ![合并输入]( {{ "/assert/20181006_3.jpg" | prepend: site.img_location }} ) 

* 3.2 打开Quick-Time Player，使用屏幕录制，设置声音输入为 **Aggregate Divice**,这样录制的视频，不但有本来的声音，还有你自己的声音(为了保证音质，推荐使用带麦的耳机)       

  ![合并输入]( {{ "/assert/20181006_5.jpg" | prepend: site.img_location }} )     





#### 参考资料：

1. [https://www.jianshu.com/p/a8ff665285de](https://www.jianshu.com/p/a8ff665285de)
2. [https://github.com/mattingalls/Soundflower](https://github.com/mattingalls/Soundflower)



