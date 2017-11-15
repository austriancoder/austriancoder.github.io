---
layout: post
title: Serial over USB
date: '2007-11-30 02:22:55'
---


Nachdem ein neuer Stack meine alten USB-Stack, welcher im Google Summer of Code für [RockBox](http://www.rockbox.org) erstellt wurde, durch einen wenig objektorientierten und nicht so generischen USB-Stack ersetzt wurde, habe ich in weniger als 20 Minuten einen serial Treiber geschrieben.  Leider ist der neue Stack noch fertig und es fehlt eine wichtige Funktionalität: Umschalten zwischen verschieden device Treibern zur Laufzeit… bald ist ja Wochenende.

Revision 15850 rockt 🙂

# modprobe usbserial vendor=0x0781 product=0x7421 debug=1
 # picocom /dev/ttyUSB0
