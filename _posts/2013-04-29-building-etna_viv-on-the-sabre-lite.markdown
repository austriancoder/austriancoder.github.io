---
layout: post
title: Building etna_viv on the sabre lite
date: '2013-04-29 19:03:10'
tags:
- imx6q
- etna_viv
---


At the moment I am playing around with a cute nice little imx6q board – [the sabre lite](http://boundarydevices.com/products/sabre-lite-imx6-sbc/).

I am running a freescale based RFS with the binary libGAL.so blob in the user space. So why
 not look into etna_viv and get it compiled. It turns out to be as simple as this.

 git clone git://github.com/laanwj/etna_viv.git cd etna_viv/native export GCABI=imx6 export CFLAGS="-D_POSIX_C_SOURCE=200809 -D_GNU_SOURCE -DLINUX -pthread" export CXXFLAGS="-D_POSIX_C_SOURCE=200809 -D_GNU_SOURCE -DLINUX -pthread" make

At the moment the GC2000 support is non existent but it should be possible to add support
 for it in the foreseeable future. To get a picture what needs to be done have a lookt at
[https://blog.visucore.com/2013/3/3/gc2000-vs-gc800](https://blog.visucore.com/2013/3/3/gc2000-vs-gc800)
