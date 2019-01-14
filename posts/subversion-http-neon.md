---
title: subversion-http-neon
date: '2013-08-28'
description:
categories:
---
subversion 添加neon，始终失败，编译了好多次一致添加不进去。

最后grep一把configure信息

configure: checking neon library
checking neon library version... 0.30.0
You have neon version 0.30.0,
but Subversion needs neon 0.29.6.
An appropriate version of neon could not be found, so libsvn_ra_neon
will not be built.  If you want to build libsvn_ra_neon, please
install neon 0.29.6 on this system.
no suitable neon found

囧。。。更新吧。
