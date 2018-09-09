---
layout: post
title: 树莓派进行SPI ROM烧录(OpenWrt)
date: 2014-09-09
categories: tech
tags: [RPi,flash]
description: 改造树莓派进行SPI烧录路由器ROM
---

#### 这是以前在新浪的老博文，迁移到此，纪念那些玩Openwrt的日子

最近又入手了一个路由器，心里痒痒又想将其改造成openwrt，但是没有烧录器，看到网上树莓派可以进行改造，折腾走起。

我们烧录的方式就是把ROM IC 拆下来，接上座子或者线，在树莓派上用flashrom 这个软件进行烧录

1. 首先找到flashrom-master.zip这个软件，找不到的话 ，文档最后会有下载的地址

2. make编译一把

3. 然后查看 flashrom -L 查看你的ROM IC是否支持在列表里面

4. 引脚的对应关系： IC引脚  -- 树莓派端口pin

    1  ->  24   
    2  ->  21  
    3  ->  17  
    4  ->  25   
    5  ->  19      
    6  ->  23   
    7,8 -> 1   
    按照这个践行连线，前面是IC的引脚，后面是树莓派的Header标号，具体为什么这样接，就不讲了

5. 进入SPI 模式  
    sudo modprobe spi_bcm2708
    sudo modprobe spidev     

6. 依次进行擦除、写入、以及验证的过程  
     sudo ./flashrom -E -V -c MX25L6445E -p linux_spi:dev=/dev/spidev0.0   
     sudo ./flashrom -w ./703N_TT.bin -V -c MX25L6445E -p linux_spi:dev=/dev/spidev0.0  
     sudo ./flashrom -r ./read.rom -V -c MX25L6445E -p linux_spi:dev=/dev/spidev0.0  

开动！

参考资料: [https://libreboot.org/docs/install/rpi_setup.html](https://libreboot.org/docs/install/rpi_setup.html)

flashrom 下载地址：  [http://pan.baidu.com/s/1mgqkYi0](http://pan.baidu.com/s/1mgqkYi0)