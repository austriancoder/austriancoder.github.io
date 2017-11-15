---
layout: post
title: Status Update
date: '2011-11-07 20:55:47'
---


Hallo zusammen.

Ich habe schon länger nichts mehr von mir hören lassen, doch nun habe ich ein Update
 bezüglich em8300 und dem langsamen aber stätigem Prozess zur Aufnahme in den Mainline Kernel.

Im Linux Kernel 3.3.0 sind kleine Änderungen für die adv7170 und adb7175 Treiber eingeflossen, welche vom em8300 Treiber benötigt werden. Somit wäre es dann möglich direkt mit dem V4L2 Subdevices zu arbeiten. Was gibt es aber sonst noch zu tun, damit der Prozess irgendwann ein Ende findet?

- bt868 Treiber in den Mainline bringen
- VB2
- Evtl die DVB-API untersuchen, ob besser als V4L2 API für Ausgbae
- Rework des Firmware-Loaders
- Locking
- …

Ich hoffe, dass ich in den nächsten Wochen wieder ein wenig Zeit finde.
