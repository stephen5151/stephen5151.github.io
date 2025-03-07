---
layout: post
title: "关于音视频数据量的计算"
author: "Stephen He"
categories: tech
tags: [tech]
image: calculate.png
---
在要计算前，要想了解下单位。  
bit是最小的单位，1bit是硬盘的一个位点。
**1B(字节)=8bit**  **1KB=1024B**  **1MB=1024KB**  **1GB=1024MB**  **1TB=1024GB** 同理更大的容量往上增1024倍。  



现在有一分钟的声音，采样频率是44.1kHz，量化位数16位（bit）  
意味着每秒采集数据44.1k个，每个数据占16bit，这是一个声道的数据，双声道就乘以2，最后结果再60秒。  
即 **44100 * 16 * 60 = 42336000(bit)**  该声音一个声道一分钟的数据量。 双声道就再乘以2，然后化单位为 **42336000 * 2 / 8 * 1024 * 1024 = 10.09(MB)  
**总结：数据量（bit）=采样频率 * 采样位数 * 声道数*时间**  

视频的数据量计算  
**时间 * 每秒像素 * 每秒帧数 * 彩色深度**  
例如：SDTV 像素625*576 帧数50i 彩色深度24。
