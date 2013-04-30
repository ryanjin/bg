---
title: 安装Fswebcam
date: '2013-04-30'
description:
- Raspberry下安装Fswebcam
categories:
- raspberry
---
安装fswebcam

	wget http://www.sanslogic.co.uk/fswebcam/files/fswebcam-20110717.tar.gz
	tar zxvf fswebcam-20110717.tar.gz
	cd fswebcam-20110717.tar.gz
	./configure
提示

	checking for gdImageCreateTrueColor in -lgd... no
	configure: error: GD graphics library not found	
安装libgd2-noxpm-dev

	sudo apt-get install libgd2-noxpm-dev
继续完成fswebcam的安装

	./configure
	checking for gdImageCreateTrueColor in -lgd... yes
	checking for gdImageStringFT in -lgd... yes
	checking for gdImageJpeg in -lgd... yes
	checking for gdImagePngEx in -lgd... yes

  		Buffer type ........... 16 bit
   		PNG support ........... yes
   		JPEG support .......... yes
   		Freetype 2.x support .. yes
   		V4L1 support .......... yes
   		V4L2 support .......... yes

	configure: creating ./config.status
	config.status: creating Makefile
	config.status: creating config.h

	make
	make install

安装完成以后运行脚本拍照

	sudo fswebcam -v -r 640x480 --no-banner /var/www/fswebcam/cam.jpg


参考 https://github.com/fsphil/fswebcam/issues/4