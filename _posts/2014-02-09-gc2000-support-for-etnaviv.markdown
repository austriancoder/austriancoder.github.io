---
layout: post
title: GC2000 support for etnaviv
date: '2014-02-09 17:22:56'
tags:
- gpu
- vivante
- gc2000
- etnaviv
---


Today I hit an important milestone for etnaviv – an open source user-space driver for the Vivante GCxxx series of embedded GPUs.
 I finally got GC2000 support to a level that it seems to work. It took me some months to get there.
 At the beginning it sounds easy to rebuild a ‘driver’ if you get readable command buffer dumps. I did start with working on a simple replay program to render a cube in the same was as the binary blob does it.
 But what should I say… it is quite boring to do everything by hand and not taking advantage of libetnaviv
 and the ‘driver’ at all. So I decided to go the hard way and try to fix/add all missing bits until it renders something.
 The good thing is that I have now some knowledge about the structure of libetnaviv, the
 dirver and mesa in general. It helps a lot if you know why stuff is done that way.

Also this is my first reverse engineering project I contributed to and even I have never done any graphics related stuff – okay I did
 some OpenGL stuff during my studies.

I try to find some more time to help to create a fully open source graphics stack for Vivante GPUs.

If have not seen it yet: Here is a short video showing the current state of etnaviv on a iMX6q (Sabre Lite).
[Video in Google+ post](https://plus.google.com/102045773664179486664/posts/aiBDNmMQRTU)
