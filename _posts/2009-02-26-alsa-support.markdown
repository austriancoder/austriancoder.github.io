---
layout: post
title: Alsa Support
date: '2009-02-26 12:19:49'
---


Nachdem das letzte Semester sehr zeitintensiv war fand ich leider sehr wenig Zeit für opensource Projekte.
 Doch im Moment genieße ich die freie Zeit die zur Verfügung habe und stecke im Moment viel Zeit in das
 vdr-plugin-dxr3.

Mein großes Ziel ist zum einen Alsa für die Soundausgabe zu unterstützten und zum anderen das Plugin
 wesentlich stabiler zu machen.
 Alsa funktioniert schon recht gut, auch wenn es noch Probleme beim Umschalten geben kann und Digital PCM
 und AC3 noch nicht unterstützt werden. Doch ich bin auf dem richtigen Weg.

Ich bin immer sehr froh über Testberichte 🙂
 Die aktuellen Sourcen gibts hier: [http://projects.vdr-developer.org/git/?p=vdr-plugin-dxr3.git;a=summary](http://projects.vdr-developer.org/git/?p=vdr-plugin-dxr3.git;a=summary)

Im Moment ist Alsa noch nicht per standard verfügbar, sonder muss in dxr3device.c von Hand aktiviert werden.
 Am besten nach folgender Zeile ausschau halten:

> audioOut = new cAudioAlsa();

diese auskommentieren und die Zeile mit cAudioOss() einkommentieren.

Viel Spaß
