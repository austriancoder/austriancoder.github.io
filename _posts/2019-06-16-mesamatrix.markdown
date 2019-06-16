---
layout: post
title: mesamatrix
date: '2019-06-16 15:40:01'
tags:
- gpu
- mesa
- etnaviv
---

You might be familiar with [mesamatrix](https://mesamatrix.net/) - a nice site to track the state of all GPU drivers provided by Mesa. Ohh.. did I say all? Let's have a closer look:

> This page is a graphical representation of the text file docs/features.txt from the Mesa repository.

So wouldn't it be sick to get etnaviv mentioned in docs/features.txt and onto the matrix?

First mesamatrix needs to know/support etnaviv. This seems to be quite simple as there is already a pull request to add a bunch of embedded GPU drivers: [Add VC4,VC5 and Vivante GPUs](https://github.com/MightyCreak/mesamatrix/pull/136)

![Comment found at mesamatrix pull request](/img/mesamatrix_pull_20190616.png)

Second we need is to add support for an easy to support extension. After skimming through the list I settled with [ARB_seamless_cubemap_per_texture](https://www.khronos.org/registry/OpenGL/extensions/ARB/ARB_seamless_cubemap_per_texture.txt)

To be fair I know that there are some UNK bits in the sampler registers and I hope one of them has something to do with seamless cubemaps. I went with a quick try-and-error approach to find the UNK bit which enables seamless cubemaps. And after 20 minutes of hacking the spec@amd_seamless_cubemap_per_texture@amd_seamless_cubemap_per_texture piglit works \o/.

The end result can be found in [in this merge request](https://gitlab.freedesktop.org/mesa/mesa/merge_requests/997). I hope to merge the changes soon and see something new in mesamatrix.