---
layout: post
title: The next steps for etnaviv
date: '2014-02-22 17:54:17'
tags:
- gpu
- imx6
- etnaviv
---


I did spend some time to find the cause for the rendering issues during running some egls2 demos. The fix is a simple one-liner and I would say that GC8xx and GC2000 are ‘equal’ now. That means general work on etnaviv can start now. Currently I am looking in different problem zones and where to start.

1. Update mesa fork
2. Start working on an improved compiler
3. Start working on an kernel interface

I think that Rob will start soon on the kernel interface and the mesa update should be doable during some hours. So I think the next big and important step is to improve the compiler. What should I say… I have basic compiler understanding, did wrote a compiler and VM during my study… thats it. I have never written a single line of glsl and I do not completely understand the Vivante GPU. So a perfect starting point for doing some hacking 🙂 The success rate will be quite low and I hope to not lose my motivation too soon.
