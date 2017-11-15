---
layout: post
title: SMBus Compatibility With an I²C Device
date: '2013-02-23 10:54:30'
tags:
- i2c
- kernel
- smbus
---


Some naive guys – like me – think that SMBus and I²C are equal expect the bus level. But in the last days I run into a problem where an at24 based EEPROM connected via SMBus triggers a bus collision after a warm reboot. After some hours of debugging – even staring minutes at a oscilloscope showing SDD and SDC lines – I started to add some dump_stack() calls into i2c_core.c file form a recent linux kernel. And I found the bad bus transaction – i2c_probe_func_quick_read(..).

But whats exactly the problem here?

> The SMBus specification describes a number of standardized
>  transactions. Each chip on the bus can support each given transaction
>  type or not. In practice, each slave chip only supports a subset of the
>  SMBus specification. The Linux i2c subsystem abuses this
>  transaction type for device detection purposes, because it is known to
>  give good results in practice, but ideally it shouldn’t do that.
>
> There have been some devices known to lock up the SMBus on Quick
>  command with data bit = 1. In most cases
>  these were write-only devices, which didn’t expect a transaction
>  starting like a read (the SMBus specification says that a Quick command
>  with data bit = 1 is writing 1 bit to the slave, but the I2C
>  specification says this is a _read_ transaction of length 0.)
>
> This SMBus Quick command thing keeps causing trouble and confusing
>  people. Not much we can do though. If your slaves don’t like the quick
>  command, just don’t send that command to them.
>
> [SMBus quick command problem](http://www.mail-archive.com/linux-i2c@vger.kernel.org/msg00209.html "SMBus quick command problem")

The solution is quite simple: use i2c_new_probed_device(..) function for probing devices on the SMBus/I²C-Bus. By the way I have found a nice comparison from TI: [SMBus vs. I²C](http://www.ti.com/lit/an/sloa132/sloa132.pdf)
