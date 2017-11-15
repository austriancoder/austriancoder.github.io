---
layout: post
title: Buffering und Sync
date: '2009-03-23 19:41:33'
---


Nachdem ich nun einen schlanken und gut dokumintierten und v.a. funktionierenden Pes-Parser habe, bin ich
 mir am überlegen, wie ich nun weitermachen sollte. Ich könnte nun Glue-Code  dem neuen Pes-Parser hinzufügen
 und Stück für Stück so weiter machen wie bis her, oder ich mache einfach dies:

> git rm dxr3syncbuffer.c
>  git rm dxr3syncbuffer.h
>  git rm dxr3demuxdevice.c
>  git rm dxr3demuxdevice.h

Das ist zwar eine brachialte Art und Weise, doch irgnedwann muss man das Buffering und Syncing neu schreiben. Nun
 geht es darum, alles wieder ohne Fehler zum compilieren zu bringen und dann das Plugin wieder so funktionstüchtig zu
 machen wie die 0.2.9 Version. Es werden große Änderungen sein, doch es wird sich auszahlen.
