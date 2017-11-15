---
layout: post
title: i.MX6 - DDR3 setup
date: '2013-07-26 15:15:04'
tags:
- ddr3
- i-mx6
---


The company I work for has designed a custom i.MX6 based board and I am the guy who
 does the board bring-up. For me the i.MX6 platform is a very good choice as support
 for the hardware in u-boot and the linux kernel is quite good. So it should not be
 too hard to get linux running on our custom board.

But wait… as I learned from my coreboot activities – memory setup is the hardest
 and most importest part. The custom board has 1GB of DDR3 on it and I started to look
 how u-boot does the DDR setup. And there I read the term DCD – Device Configuration Data.

DCD does contain the init sequence for DDR3 and I had to look up some stuff in the
 “[i.MX 6Dual/6Quad Applications Processor Reference Manual](http://cache.freescale.com/files/32bit/doc/ref_manual/IMX6DQRM.pdf "i.MX 6Dual/6Quad Applications Processor Reference Manual")” to find out that this must
 be some kind of black magic. I tried my luck with the DDR3 Stress Tester from Freescale
 and failed. It was so hard to get all those register correct if you do not know much about
 DDR3 at all.

Luckily I got a hint that in the Freescale commuity is something which could help me – thanks Fabio. It turns out to be an Excel sheet where I filled in few values and got a DDR3 init script for the DDR3 Stress Tester.

10 Minutes after I got the Excel sheet into my hands it looks like I got the memory up
 and running – nice!

The “magic” Excel sheet can be found [here.](https://community.freescale.com/docs/DOC-94917 "i.Mx6DQSDL DDR3 Script Aid")
