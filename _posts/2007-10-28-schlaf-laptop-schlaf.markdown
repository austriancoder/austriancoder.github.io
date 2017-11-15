---
layout: post
title: Schlaf Laptop schlaf...
date: '2007-10-28 16:37:14'
---


Suspend war und ist immer noch ein Knackpunkt von Linux. Doch zum Glück kann ich sagen, dass sich die Situation verbessert hat und nun ist es ohne Suspend2 Patches möglich mit einem aktuellen Kernel 2.6.23 Suspend2Ram und Supend2Disk zu verwendet. Nach einer schnellen Kernelconfig-Änderung und dem hinzufügen von ***resume=/dev/hda2***zu den Boot-Pararmetern genügten schon um von Kernel-Seite alles bereitzustellen.

Jetzt fehlt nur noch der Userspace 🙂 Unter Gentoo reicht ein  einfaches ***emerge sys-power/suspend ***und dem Supendieren steht nichts mehr im Weg. Unter KDE ist KPowersave sehr zu empfehlen.
