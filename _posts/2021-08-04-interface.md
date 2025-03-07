---
layout: post
title: "音视频接口以及传输信号的归纳总结"
author: "Stephen He"
categories: tech
tags: [tech]
image: XLR.jpg
---
# 1、音频接口  
### (1) RCA模拟音频  
RCA接头，就是平时说的莲花头。RCA接口采用同轴[^1]传输信号的方式，中轴用来传输信号，外沿一圈的接触层用来接地。**每一根RCA线缆负责传输一个声道的音频信号，所以立体声信号，需要使用一对线缆。** 一般立体声的RCA音频接口，右声道用红色标注，左声道用蓝色或白色标注。  
![RCA](../assets/img/RCA.png)    
<center style="font-size:14px;color:#696969;">RCA接头</center>  


### (2) 平衡模拟音频  
平衡模拟音频（Balanced Analog Audio）接口使用两个通道分别**传送信号相同而相位相反的信号**。接收端设备将这两组信号相减，干扰信号就被抵消掉，从而获得高质量的模拟信号。平衡模拟音频通常采用**XLR接口**[^2]和**大三芯**[^3]接口，大三芯接口采用6.35mm插头。平衡模拟音频线适合高级模拟音响器材或专业音频设备上。  
![XLR](../assets/img/XLR2.jpg)    
<center style="font-size:14px;color:#696969;">XLR接头</center>    




### (3) 非平衡模拟二芯TS  
二芯的TS接头可以用来传输非平衡的单声道音频信号，电吉他、贝斯常用的连接线。*（另外注意电吉他、贝斯不能直接接入调音台，因为是高阻抗，信号很小，要通过接一个DI盒）*
![TS](../assets/img/TS.png)    
<center style="font-size:14px;color:#696969;">TS接头</center>    


>何为平衡信号和非平衡信号：  
>>声波转换成电信号后，直接传送的就是**非平衡信号**   

>>如果把原始信号反相180度，然后原始信号和反相信号同时传送的那组信号，叫**平衡信号**。平衡传输能利用相位抵消原理，将音频信号传输过程中受到的其他干扰降至最低，值得注意的是XLR接口也跟TRS接口[^3]一样，可以传输非平衡信号，因此光从借口来看，是分不出传输的是平衡还是非平衡的信号。  

>扩展信息
>>**不能说一个平衡信号线就能保证传输的是平衡信号**   
>>**一根电缆里面有相互绝缘的2条或3条,就叫做2芯，3芯**  


### (4) 小三芯插头（3.5mm接头）  
多用于电脑及便捷式音源。  
![3.5mm](../assets/img/3.5.png)   
<center style="font-size:14px;color:#696969;">3.5mm接头</center>    


### (5) S/PDIF数字接口(数字以PCM脉冲编码调制传输)  
S/PDIF是*Snoy/Philips Digital Interconnect Format*缩写，数字接口，一种软接口，一般**物理上用的是数字同轴RCA接口**。这是索尼与飞利浦公司合作开发的一种**民用数字音频接口协议**。之后由于被广发采用，它成为了**民用数字音频格式标准**。S/PDIF和AES/EBU有略微不同的结构。音频信息在数据流中占有相同位置，使得这两种格式在原理上是兼容的。     
![S/PDIF](../assets/img/SPDIF.png)   
<center style="font-size:14px;color:#696969;">S/PDIF</center>   



### (6) 数字音频接口之同轴接口  
数字同轴 (*Digital Coaxial*)是利用S/PDIF接口输出数字音频接口。同轴数字接口： **RCA同轴数字接口**和**BNC接口**。前者外观和模拟RCA接口没什么区别，但线不能够混用，由于RCA同轴线是固定**75欧姆阻抗**，混用线会造成声音传输的不稳定，使音质下降。后者是有锁紧设计，不易松动。
![BNC接头](../assets/img/tongzhou1.png)   
<center style="font-size:14px;color:#696969;">BNC接头</center>
![RCA接头](../assets/img/tongzhou2.png)  
<center style="font-size:14px;color:#696969;">RCA接头</center>  

>与S/PDIF相当的是AES，底层通行架构都是RS-422(一种串行通行标准)[^5]，两者的传输格式都是以192帧为单位，每一帧之间4个bit的停止位用于同步。S/PDIF的传输协议就是阉割版的AES，去掉了一些控制指令，但数据帧与AES相同，理论上可以使用转换器S/PDIF与AES之间转换，***但AES是110Ω***标准，阻抗之间并不匹配。



### (7) 数字音频接口之光纤接口  
光纤接口（*TOSLINK*），器材上一般标为“*Optical*”。它的物理接口分为两种类型，一种是**标准方头**，另一种是在便携设备上常见的外观与3.5mm TRS接头类似的**圆头**。由于它是**以光脉冲的形式**来传输数字信号，因此单从技术角度来看，它是传输速度最快的.光纤同样采用S/PDIF接口输出，其*带宽高，信号衰减小*，常用于DVD播放器和AV功放，***支持PCM数字音频信号，Dolby以及DTS音频信号***。光纤连接可以实现电器隔离，阻止数字噪音通过地线传输，有利于提高DAC[^4]的信噪比。但由于它需要光线发射口和接受口，而这两个口的光电转换需要用光电二极管，光纤和光电二极管之间不可能有紧密的接触，从而会产生数字抖动类的失真。*它在数字抖动方面比同轴差很多*   
![光纤接头](../assets/img/guangxian.png)  
<center style="font-size:14px;color:#696969;">光纤接头</center>  


### (8) 凤凰接口  
凤凰头(*Cresnet*)  
![凤凰接头](../assets/img/fh.png)  
<center style="font-size:14px;color:#696969;">凤凰接头</center>    
![凤凰头转换平衡](../assets/img/fhtoph.png)  
<center style="font-size:14px;color:#696969;">凤凰头转换平衡</center>  
![凤凰头转换非平衡](../assets/img/fhtofph1.png)  
<center style="font-size:14px;color:#696969;">凤凰头转换非平衡</center>  
![R凤凰头转换非平衡](../assets/img/fhtofph2.png)  
<center style="font-size:14px;color:#696969;">凤凰头转换非平衡</center>  



### (9) 音响插头欧姆头  
欧姆头，又叫贝尔头，塞克头。欧姆接头分为1+，1-,2+,2-,因为怕短路，因此正极比负极的接口范围较小些。
![欧姆接头](../assets/img/oumu1.png)  
<center style="font-size:14px;color:#696969;">欧姆接头</center>  






# 2、视频接口介绍  
### (1) VGA接口  
VGA(*Video Graphics Array视频图形阵列，又叫D-Sub*)。最早的VGA接口最大只能支持640 * 480分辨率，所以当时把640 * 480分辨率称为VGA分辨率目前VGA接口和视频线最大能支持2048 * 1536的分辨率，但新款显卡和显示器已经弃用了VGA接口。在接口设计上，它始终是为了CRT屏幕，而现在的显示屏已经是LED屏幕，所以VGA接口模拟转数字信号会造成影像细节丢失 *在VGA线进行长距离传输，或采用不适配的分辨率和刷新率，偶尔会看到显示器出现虚影和闪屏现象。*  另外，VGA接口是**不支持传输音频的**  
![VGA接头](../assets/img/VGA.png)  
<center style="font-size:14px;color:#696969;">VGA接头</center>  


### (2) DVI数字视频接口  
DVI(*Digital Visual Interface*)数字视频接口  
![DVI接头](../assets/img/DVI.png)  
<center style="font-size:14px;color:#696969;">DVI接头</center>  
![DVI接头](../assets/img/DVI1.png)  
<center style="font-size:14px;color:#696969;">不同类型的DVI接头</center>  




### (3) HDMI接口  
HDMI(*High Definition Multimedia Interface*)高清多媒体接口。HDMI接口 ***不仅传输带宽大，而且还可以同时传输未压缩音视频信号***。HDMI的数据传输包括TMDS0,TMDS1,TMDS2三个通道和一个时钟。  
>如果传输的是Video Data（视频信息），并且格式为RGB，那么会占用三个通道的所有24bit输入，Channel0[7:0]用户传输B，Channel1[7:0]用于传输G，Channel2[7:0]用于传输R。

>  2.如果传输的是Data Island（数据包），则占用三个通道共10bit输入，Channel0[3:2]用于传输Data Island Header（包头），Channel1[0:3]与Channel2[0:3]用于传输Data Island Content（包内数据）。

>3.如果传输的是Preamble（控制信息），则占用1，2两个通道共4bit输入，Channel1[1:0]与Channel2[1:0]分别为CTL0，CTL1，CTL2，CTL3，用于判断接下来输入的是Video Data或者Data Island   

![HDMI接头](../assets/img/HDMI1.png)  
<center style="font-size:14px;color:#696969;">HDMI接头</center>   
![HDMIspeed](../assets/img/HDMIspeed.png)  
<center style="font-size:14px;color:#696969;">HDMI接头不同的传输速度</center>  
![HDMItype](../assets/img/HDMItype.png)  
<center style="font-size:14px;color:#696969;">HDMI类型</center>   




### (4) DP数字接口  
常见的DP有全尺寸接口和Mini尺寸接口，两种尺寸的接口版本性能上是一致的。*DP接口的数据传输形式跟网线和USB线相似，是以数据包形式进行传输*   
![DP接头](../assets/img/DP.png)  
<center style="font-size:14px;color:#696969;">DP接头</center>  
![DP传输原理](../assets/img/DP1.png)  
<center style="font-size:14px;color:#696969;">DP传输原理</center>  
![DP速度](../assets/img/DP2.png)  
<center style="font-size:14px;color:#696969;">DP速度</center>  
![DP](../assets/img/DP3.png)  
<center style="font-size:14px;color:#696969;">DP扩展</center>  


### (5) USB type-c  
USB Type-c(*Universal Serial BUG TYPE-C*)通用串行总线类型C。将USB接口运用在视频传输上，应该归功于DP技术。因为既然DP可以用数据包的形式传输视频，所以出现接口使用USB（普及度高）传输DP数据包的技术，它跟DP接口的传输特性是一样的。  
![USB-C](../assets/img/USPTYPE.png)  
<center style="font-size:14px;color:#696969;">USB type-C</center>  
![USBspeed](../assets/img/USB.png)  
<center style="font-size:14px;color:#696969;">不同USB版本的速度</center>  




### (6) 分量视频接口  
分量视频接口也叫色差输出、输入接口(*3RCA*)，把视频信号的亮度信号和色彩信号分开来，这样视频信号包括了分开传输的一路亮度信号和两路色差信号，因而避免了信号之间的串扰。与复合电视信号和S端子相比有更高的图像质量。  
![3RCA](../assets/img/3RCA.png)  
<center style="font-size:14px;color:#696969;">3RCA接口</center>  



### (7) 复合视频信号   
复合视频信号，定义为包括亮度和色度的单路模拟信号，也即从 *全电视信号中分离出伴音后的视频信号，这时的色度信号还是间插在亮度信号的高端。*一般接头为BNC、RCA。   
![复合视频信号](../assets/img/fuhe.png)  
<center style="font-size:14px;color:#696969;">复合视频信号接口</center>  


### (8) S-端子
S-端子也称（Y/C），也叫“二分量视频接口”。S指的是“SEPARATE（分离）”，*它将亮度和色度分离输出，避免了混合视讯讯号输出时亮度和色度的相互干扰*。S接口实际上时一种五芯接口，由两路视亮度信号、两路视频色度信号和一路公共屏蔽底线组成。  
![S-端子](../assets/img/S.jpg)  
<center style="font-size:14px;color:#696969;">S-端子接口</center>  


>拓展信息  
>>双绞线（twisted pair，TP线）是一种综合布线工程中最常用的传输介质，是由两根具有绝缘保护层的铜导线组成的。把两根绝缘的铜导线按一定密度互相绞在一起，每一根导线在传输中辐射出来的点播会被另一根线上发出的电波抵消，有效降低信号干扰的程度。

>>同AV接口相比，由于它不再进行Y/C混合传输，因此也不需要亮色分离和解码工作，而且*使用各自独立的传输通道在很大程度上避免了视频设备内信号串扰而产生的图像失真，极大地提高了图像的清晰度*。  

>>S-Video仍要将两路色差信号（Cr Cb）混合为一路色度信号C，进行传输后在像是设备内解码为Cb和Cr进行处理，这样多少仍会带来一定信号损失而产生失真（虽然失真很小，但在严格的广播级视频设备下进行测试时仍能发现），而且由于Cr Cb的混合导致色度信号的带宽也有一定限制。  



[^1]: 同轴线：指有两个同心导体，导体和屏蔽层又共用同一轴心的电缆，线的阻抗是**75欧姆**
[^2]: XLR接口也叫卡侬头，可以传输音频平衡信号，常见的是3脚的2正3负1接地。也有2脚、4脚、5脚的。
[^3]: 也叫TRS接口，Tip（signal）、Ring(signal)、Sleeve(ground)，可以传输平衡信号。3.5mm接头叫“小三芯”,6.35mm接头叫大三芯。
[^4]: 数模转换器，模数转换是ADC   
[^5]: RS-422，比RS-232高级，但比不上RS-485。RS-422可以在1.2m的双绞线上提供最高10Mbps传输速率，而RS-485可以提供最高35Mbps，距离变长后，RS-422的传输速度会下降，典型的AES/EBU最大线缆长度为90米。  


>关于线的一些玄学问题  
>>1、高档数字同轴线有没有用？   
>>>超过1.2米有用，因为RS-422的传输特性，距离越长传输速率会下降，使用高档的线可以减少误码率，延长传输距离，不过有可能的话，使用6类双绞线可以获得更好的性能。但这些手段效果非常有限且仅在超过1.2米以上的距离才起作用。  
>>外部时钟是什么？有用吗？
>>>外部时钟，其实本质就是通信领域常用的帧同步器，在减少传输误码率方面是非常有用的，指示音频领域远比通信领域要求低，用不着高级的位同步器，用较低端的字同步器就够了。



--------------------------------------------

***本文章是我学习音视频的接口，收集资料总结归纳的，如有侵权会立马删除***


参考资料：  
[1]:<https://max.book118.com/html/2020/0820/8117113122002134.shtm>  
[2]:<https://blog.csdn.net/qq_29214249/article/details/54924010>  
[3]:<https://blog.csdn.net/ytffhew/article/details/83618007>  
[4]:<https://www.21ic.com/article/894827.html>  
[5]:<https://zhuanlan.zhihu.com/p/35197368>  
[6]:<https://www.cnblogs.com/guanghe/p/12512055.html>
[7]:<https://www.office26.com/computer/computer_16506.html>
[8]:<http://www.headphoneclub.com/thread-278047-1-1.html>
