---
layout: post
title: Linux und HP COLORADO 20GBe(extern)
date: '2010-01-19 11:31:34'
tags:
- extern
- hp-colorado
---


Im Moment bin ich damit konfrontiert, Backups von einem alten exteren Bandlaufwerk wiederherzustellen. Das große Ziel ist es an einen Bruchteil der Daten auf dem Bandlaufwerk Zugang zu bekommen.

![](http://www.buycoms.com/pic/product/129/14085/TAB6_2.JPG "HP Colorado 20 GB")Mein Kunde verwendet im Moment einen aktuellen Recher (Quad-Core) mit einem ebenso aktuellen Windows. Blöderweise werden keine Treiber von HP für diese Windows-Version zur Verfügung gestellt und ich musste nach einer Alternative ausschau halten. Und hier glänzt Linux. Ich verwende einen 2.6.32 Kernel und konnte mit diesem erfolgreich das externe Bandlaufwerk (Parallel-Port) erkennen/verwenden.

Dazu müssen folgende Module compiliert und geladen werden:

- epat
- paride
- pt

Ist das Bandlaufwerk verbunden und die Module geladen sollte folgendes via *dmesg *zu sehen sein.

> paride: epat registered as protocol 0
>  pt: pt version 1.04, major 96
>  pt0: Sharing parport0 at 0x378
>  pt0: epat 1.02, Shuttle EPAT chip c6 at 0x378, mode 2 (8-bit), delay 1
>  pt0: HP COLORADO 20GBe, master, blocksize 512, 9209 MB
