---
layout: post
title: 'etnaviv: kmscube'
date: '2015-09-25 21:39:10'
tags:
- gpu
- imx6
- mesa
- render-only
- etnaviv
---


Last Friday I got kmscube successfully running with mesa and the new etnaviv DRM kernel driver. At this time I got it not really pixel perfect and I spend some nights to get it fixed. It turns out that I need a small mesa hack to get the rendering correct.

<iframe allowfullscreen="" frameborder="0" height="473" src="https://www.youtube.com/embed/vjIBow3M-C4?feature=oembed" width="840"></iframe>

You may ask why did it so long to get it working? Let me explain it to you.

The Vivnate GPU is a so called render-only GPU which does not have any kind of scanout logic in it. It can only render to physical memory and this only in a tiled memory layout. So we need to use the resolve engine found on the GPU to de-tile the rendered image and blit it to the dumb buffer. Currently mesa has  no software support for this kind of hardware, but I think that could change soon.

I think that this is a huge step into the right direction. All the needed sources can be found on [my github account](https://github.com/austriancoder). At the moment I am cleaning up the code and shortly I will send out RFC patch series for <strike>libdrm and</strike> mesa. Currently some hacks are needed to get it up an running so there is still a lot left to do.

<strike>Yes I think libdrm is needed and should not be part of the gallium driver. I even think xf86-video-armada could be using libdrm-etnaviv sooner or later. This one of the topics on my huge TODO list.</strike>

Russell does not want to maintain a 3rd GPU backend and with that fact I think I will merge the etnaviv libdrm part directly into the driver. Let’s see how the patch series gets accepted.

I think this the perfect time to say “thank you” to some guys. Wladimir thanks for the wonderful code basis you provided for the whole etnaviv project. Rob, thanks for your patience with me – at this point in time I was a complete newbie in the mesa source code and the whole GPU world. Thanks NVIDIA for their wonderful render-only patch. Emil thanks for helping me out with ideas to get render-only into a working state. Also quite important for spare-time open source development is a hardware sponsor. In may case I want to thank [SolidRun](http://solid-run.com/) for sending me two devices for etnaviv development purposes.
