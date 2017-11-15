---
layout: post
title: 'Couldn''t register serial port 0000:02:0a.2: -28'
date: '2012-10-31 09:10:23'
tags:
- driver
- kernel
- serial
---


I run into a problem where I have a device which has two normal serial ports and some on a PCI device.
 After booting the kernel I got this error line:

 Couldn't register serial port 0000:02:0a.2: -28

In order to get more than 2 serial ports working, I “fixed” my currently used kernel config:

 CONFIG_SERIAL_8250_NR_UARTS=32 CONFIG_SERIAL_8250_RUNTIME_UARTS=6
