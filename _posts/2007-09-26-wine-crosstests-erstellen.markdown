---
layout: post
title: Wine Crosstests erstellen
date: '2007-09-26 01:02:30'
---


Nachdem ich im Moment ein paar kleine Patches für Wine beisteuern will, möchte ich natürlich meine Änderungen auf einem Windows-System testen. Hierfür bietet Wine ein **make crosstest** an. Doch damit dies unter Gentoo funktioniert, muss man folgendes ausführen:

**# emerge crossdev && crossdev i386-mingw32**

Danach muss man nur noch **./configure && make crosstest** im Wine-Verzeichnis ausführen und man bekommt Binaries für Windows.
 Happy Hacking
