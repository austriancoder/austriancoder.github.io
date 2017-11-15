---
layout: post
title: Pes-Parser rewrite done
date: '2009-04-19 19:33:23'
---


Habe soeben mal einen Tree gepusht und darin enthalten ist ein der neue Pes-Parser. Desweiteren habe ich den alten
 Source ordentlich aufgeräumt. Dabei bin ich schon auf die nächste Baustelle getroffen.

> cFixedLengthFrame oder warum doppele Datenhaltung

Im Moment wird aus dem Pes-Stream ein cDxr3PesFrame definiert, welcher wichtige Informationen ala Pes, Payload etc.
 beinhaltet. Dann wird – unter gewissen Umständen – dieser cDxr3PesFrame in einen cFixedLengthFrame kopiert und im
 SyncBuffer verarbeitet.

Nun habe ich die Idee, den cDxr3PesFrame überall zu verwenden… aus diesem Grund werde ich als erstes die Datenstruktur
 zur Speicherung von Frames im Syncbuffer auf eine LinkedList abändern. Danach wird schrittweise der cFixedLengthFrame
 eliminiert. Diese Designänderung macht den Ablauf im Plugin wesentlich einfacher.

Pes-Stream —> wird zu —> cDxr3PesFrame —> wird in SynBuffer gespeichert —> wird via Output-Thread ausgegeben

Mal schauen, wie lange ich für die Änderungen brauche und viele neue Bugs ich einscheusen kann 🙂
