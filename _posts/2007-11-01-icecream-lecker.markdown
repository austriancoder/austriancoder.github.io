---
layout: post
title: Icecream.. *lecker*
date: '2007-11-01 18:39:50'
---


Wer [Gentoo](http://www.gentoo.org "Gentoo Linux") verwendet oder sehr viel Code compilieren muss, sollte sich Gedanken machen wie man das Compileren beschleunigen könnte. Eine Lösung wäre die Verwendung eines Compile-Clusters. Ich habe mich hierbei für [Icecream](http://en.opensuse.org/Icecream "Icecream") entschieden. Wie immer eine kleine Installationsanleitung für Gentoo 🙂

- # emerge sys-devel/icecream
- # rc-update add icecream default
- */etc/conf.d/icecream* nach eigenen Wünschen bearbeiten*
- # /etc/init.d/icecream start

Diese Schritte auf allen Gentoo Maschienen durchführen, welche am Compile-Cluster teilhaben sollen.

Nachdem der Cluster nun einsatzbereit ist, muss nur noch */etc/make.conf* und **PATH** angepasst werden, damit der Cluster verwendet werden kann.

- # export PATH=/usr/lib/icecc/bin/:$PATH
- # PREROOTPATH=”/usr/lib/icecc/bin” in */etc/make.conf* hinzufügen

Nun wird bei jedem emerge der Cluster verwendet und auch bei normalen Compile-Aufgaben. Im Moment habe ich einen kleinen Compile-Cluster bestehend aus 3 Gentoo-Rechner…

Happy Hacking…

* Im Compile-Cluster darf es nur einen Node mit ICECREAM_RUN_SCHEDULER=”yes” geben.
