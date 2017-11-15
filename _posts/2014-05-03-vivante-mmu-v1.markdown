---
layout: post
title: Vivante MMU v1
date: '2014-05-03 20:25:35'
tags:
- gpu
- mmu
- vivante
- etnaviv
---


I did spend quite some time the last days to figure out how the MMU v1 could work and what all the code in the v4 Kernel sources does. It took quite some time and a little hint from Russel to finally understand it. So lets start with the technical details.

The MMU uses a page table with a maximum size of 256KB. Where each Page Table Entry (PTE) is 4 byte long. The used page size is 4K and can not be changed via some registers etc.
 Lets have a look at the bit layout of a PTE.

[![vivante_mmuv1](/wp-content/uploads/2014/05/vivante_mmuv1-1024x86.png)](/wp-content/uploads/2014/05/vivante_mmuv1.png)
 What does all that code in the v4 driver? In the end it turned out to be a ‘simple’ memory manager. All the code is needed to keep track of which pages are mapped into the GPU address area. Index 0 of the big page table array maps directly to GPU address 0x80000000 and index 1 maps directly to 0x80001000. We can quite easily map Linux kernel pages into the address range of the GPU.

The solution I am working on will use drm_mm as memory manager and the iommu framework to keep the page table in sync.
