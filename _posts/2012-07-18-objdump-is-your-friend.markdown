---
layout: post
title: objdump is your friend
date: '2012-07-18 13:41:35'
---


Lets image you are working on a coreboot port for some mainboard and you are a very glad guy cause you have a jtag interface or something similar and you notice a hang, which could be caused by a never ending loop or some other mysterious stuff – all you know is the current instruction pointer.

 objdump -S ./build/cbfs/fallback/coreboot_ram.elf

and search for the address of the instruction pointer – may it help you to figure out whats
 going on 🙂
