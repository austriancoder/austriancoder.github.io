---
layout: post
title: Add vendor specific information's to a coreboot rom
date: '2013-02-05 12:54:43'
---


Sometimes it is needed to add some vendor specific information’s like a version string
 to a generated coreboot rom. For this example we assume we want the area from 0x00 to 0x30
 for such kind of data.

The first idea is to use cbfstool. Thanks to some guys in the IRC channel it looks like the
 current build system does something like:

 cbfstool -o $$(( $(CONFIG_ROM_SIZE) - $(CONFIG_CBFS_SIZE) )) ...

So all we need is to change CBFS_SIZE to ROM_SIZE – 0x30 in .config file.

 ... CONFIG_CONSOLE_SERIAL8250=y # CONFIG_USBDEBUG is not set # CONFIG_K8_REV_F_SUPPORT is not set CONFIG_CPU_ADDR_BITS=32 CONFIG_BOARD_ROMSIZE_KB_2048=y # CONFIG_COREBOOT_ROMSIZE_KB_64 is not set # CONFIG_COREBOOT_ROMSIZE_KB_128 is not set # CONFIG_COREBOOT_ROMSIZE_KB_256 is not set ... CONFIG_CORE_GLIU_500_266=y CONFIG_PLLMSRhi=0x39c # CONFIG_NORTHBRIDGE_AMD_AGESA is not set # CONFIG_AMD_NB_CIMX is not set # CONFIG_NORTHBRIDGE_AMD_CIMX_RD890 is not set CONFIG_CBFS_SIZE=0x1FFFD0 # # Southbridge # CONFIG_SOUTHBRIDGE_AMD_CS5536=y ...

This results in the wanted result:

 ... coreboot.rom: 2048 kB, bootblocksize 688, romsize 2097152, offset 0x30 alignment: 64 bytes, architecture: x86 Name Offset Type Size vsa 0x30 stage 55124 config 0xd7c0 raw 2810 (empty) 0xe300 null 7256 fallback/romstage 0xff80 stage 19339 fallback/coreboot_ram 0x14b80 stage 38852 fallback/payload 0x1e380 payload 21831 (empty) 0x23900 null 1950728

And here the file based prove:

 # hexedit build/coreboot.rom 00000000 FF FF FF FF FF FF FF FF ........ 00000008 FF FF FF FF FF FF FF FF ........ 00000010 FF FF FF FF FF FF FF FF ........ 00000018 FF FF FF FF FF FF FF FF ........ 00000020 FF FF FF FF FF FF FF FF ........ 00000028 FF FF FF FF FF FF FF FF ........ 00000030 4C 41 52 43 48 49 56 45 LARCHIVE 00000038 00 00 D7 54 00 00 00 10 ...T.... 00000040 00 00 00 00 00 00 00 28 .......(
