---
layout: post
title: PesFrame reworking
date: '2009-03-23 10:34:58'
---


Heute habe ich wieder ein wenig Zeit gefunden, um am dxr3 Plugin zu arbeiten und bin im Moment
 an der PesFrame-Baustelle dran. Der jetzige Source ist leider nicht gerade sehr übersichtlich und
 verständlich geschrieben. Aus diesem Grund wird die PesFrame KLasse komplett neu geschrieben und
 nach meiner Einschätzung wesentlich besser zu verstehen und auch von der Laufzeit optimiert, da kein
 cDxr3SafeArray verwendet wird – wozu auch.

Ich bin mir auch im klaren darüber, dass die jetzige git Version evt nicht so stabil läuft wie die 0.2.9, doch
 das ist nur normal, wenn man viele Dinge über den Haufen wirft und neu erfindet. Gut Ding brauch seine Zeit.

PS: Alsa Audioausgabe ist hin und wieder buggy und bei einigen funktioniert garnix – keine Angst, dass steht auch
 auf meiner TODO 🙂
