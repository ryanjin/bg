---
title: Rapberry Pi 使用DHT22测量温度适度
date: '2013-05-08'
description:
categories:
---


淘宝购买的一批零件今天到货了，包括DHT22,红外，光感，lcd等。

先把DHT22替换再用的DHT11。

先说一下，为什么需要DHT22,原先用的DHT11不错就是精度太低，目测精度是1读，这下曲线就不怎么好看了，基本这个曲线是平的，所以用DHT22替换，怎么说DHT22精度也有0。1度把。

记得有个地方看到篇博文，说DHT11和DHT22几乎兼容，于是，接下来，把DHT22替换上去。

先执行了一把测温度的程序，悲剧，读出来的4个值显然和DHT11的不一样。

无奈，上Github上着了一份DHT22的代码，原来DHT22读出来的数据比DHT11更精确因此需要按照一定的算法转换。

	float t, h;
    h = (float)dht22_dat[0] * 256 + (float)dht22_dat[1];
    h /= 10;
    t = (float)(dht22_dat[2] & 0x7F)* 256 + (float)dht22_dat[3];
    t /= 10.0;
    if ((dht22_dat[2] & 0x80) != 0)  t *= -1;

这下没问题了。偶也！！

参考
---
1 [DHT22 代码](https://github.com/technion/lol_dht22/blob/master/dht22.c) 使用WiringPi
