---
layout: post
title: v4l2-em8300 - EEPROM dumps
date: '2011-05-21 21:26:04'
---


[ 4204.966614] Sigma Designs EM8300 0000:00:09.0: PCI INT A -> Link[LNKB] -> GSI 5 (level, low) -> IRQ 5
 [ 4204.966637] em8300-0: EM8300 8300 (rev 2)
 [ 4204.966642] bus: 0, devfn: 72, irq: 5,
 [ 4204.966647] memory: 0xcfe00000.
 [ 4204.966998] em8300-0: mapped-memory at 0xf9600000
 [ 4204.967163] em8300-0: using MTRR
 [ 4205.038676] bus 0: i2c scan: found device @ 0x8a  [bt865]
 [ 4205.169007] bus 1: i2c scan: found device @ 0xa0  [eeprom]
 [ 4205.215170] i2c i2c-2: client [eeprom] registered with bus id 2-0050
 [ 4205.268272] full 256-byte eeprom dump:
 [ 4205.268284] 00: 10 22 00 00 00 00 00 01 00 00 00 00 00 00 00 00
 [ 4205.268299] 10: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
 [ 4205.268313] 20: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
 [ 4205.268327] 30: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
 [ 4205.268340] 40: ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
 [ 4205.268355] 50: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
 [ 4205.268368] 60: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
 [ 4205.268381] 70: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 55
 [ 4205.268394] 80: ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
 [ 4205.268408] 90: ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
 [ 4205.268422] a0: ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
 [ 4205.268436] b0: ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
 [ 4205.268450] c0: ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
 [ 4205.268465] d0: ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
 [ 4205.268479] e0: ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
 [ 4205.268493] f0: ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff ff
 [ 4205.268510] em8300-0: detected card: DXR3 with BT865.
 [ 4205.268517] em8300-0: Chip revision: 2
 [ 4205.276298] bt865 1-0045: chip found @ 0x8a (em8300 i2c driver #0-0)
 [ 4205.276910] i2c i2c-1: client [bt865] registered with bus id 1-0045
