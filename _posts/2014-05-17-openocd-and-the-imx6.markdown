---
layout: post
title: OpenOCD and the iMX6
date: '2014-05-17 17:24:35'
tags:
- imx6
- jtag
- openocd
---


[![olimex](/wp-content/uploads/2014/05/olimex-768x1024.jpg)](/wp-content/uploads/2014/05/olimex.jpg)
 Sometimes is is quite handy to have access to a JTAG interface to look more deeply into problems.  The weapon of choice is an [Olimex ARM-USB-OCD-H JTAG](https://www.olimex.com/Products/ARM/JTAG/ARM-USB-OCD-H/) in combination with [OpenOCD](http://openocd.sourceforge.net/ "OpenOCD") 0.8.0.
 First we will need to install OpenOCD.

1. apt-get install libftdi-dev
2. Download and extract OpenOCD 0.8.0
3. run ./configure
4. run make && make install

This should give you an OpenOCD installation with the following configuration:

 OpenOCD configuration summary -------------------------------------------------- MPSSE mode of FTDI based devices yes (auto) ST-Link JTAG Programmer yes (auto) TI ICDI JTAG Programmer yes (auto) Keil ULINK JTAG Programmer yes (auto) Altera USB-Blaster II Compatible yes (auto) Segger J-Link JTAG Programmer yes (auto) OSBDM (JTAG only) Programmer yes (auto) eStick/opendous JTAG Programmer yes (auto) Andes JTAG Programmer yes (auto) Versaloon-Link JTAG Programmer yes (auto) USBProg JTAG Programmer yes (auto) Raisonance RLink JTAG Programmer yes (auto) Olimex ARM-JTAG-EW Programmer yes (auto) CMSIS-DAP Compliant Debugger no

Now its time to check if a debugger connection can be established. As the JTAG is usb based you should see it via lsusb.

 Bus 002 Device 005: ID 15ba:002b Olimex Ltd. ARM-USB-OCD-H JTAG+RS232 Device Descriptor: bLength 18 bDescriptorType 1 bcdUSB 2.00 bDeviceClass 0 (Defined at Interface level) bDeviceSubClass 0 bDeviceProtocol 0 bMaxPacketSize0 64 idVendor 0x15ba Olimex Ltd. idProduct 0x002b ARM-USB-OCD-H JTAG+RS232 bcdDevice 7.00 iManufacturer 1 Olimex iProduct 2 Olimex OpenOCD JTAG ARM-USB-OCD-H iSerial 3 OLWI19GT bNumConfigurations 1 [...]

At this point OpenOCD should be able to connect to the JTAG. For the beginning you only need to provide the interface and target scripts. In my case the following works.

 christian@chgm-pc:~$ sudo openocd -f interface/ftdi/olimex-arm-usb-ocd-h.cfg -f target/imx6.cfg Open On-Chip Debugger 0.8.0 (2014-05-05-11:14) Licensed under GNU GPL v2 For bug reports, read http://openocd.sourceforge.net/doc/doxygen/bugs.html Info : only one transport option; autoselect 'jtag' Warn : imx6.sdma: nonstandard IR value adapter speed: 1000 kHz Info : clock speed 1000 kHz Info : JTAG tap: imx6.dap tap/device found: 0x4ba00477 (mfg: 0x23b, part: 0xba00, ver: 0x4) Info : TAP imx6.sdma does not have IDCODE Info : JTAG tap: imx6.sjc tap/device found: 0x2191e01d (mfg: 0x00e, part: 0x191e, ver: 0x2) Info : imx6.cpu.0: hardware has 6 breakpoints, 4 watchpoints Info : number of cache level 1 Info : imx6.cpu.0 cluster 0 core 0 multi core
