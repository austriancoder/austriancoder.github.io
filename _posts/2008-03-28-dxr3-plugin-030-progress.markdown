---
layout: post
title: dxr3-plugin 0.3.0 progress
date: '2008-03-28 21:59:25'
---


Hallo zusammen,

habe heute ein wenig Zeit gefunden, und habe nun einen Lippen-Synchronen Ton mit passendem Bild 🙂
 Leider ist der A/V-Sync Code noch nicht sehr ausgereift und deswegen geht beim Umschalten entweder Bild
 oder Ton verloren. Das ‘Problem’ sollte ich über das Wochenende gefixt haben und dann kann ich wieder
 einen Punkt aus meiner ToDo streichen.

Als nächstes werde ich entweder das OSD angehen, oder eine Infrastruktur entwickeln, damit der *GrabImage*-API
 Aufruf funktioniert bzw das Spektrum-Analyser PCM-Daten vom Plugin bekommt.

Ein Valgrind-Test könnte evt auch nicht schaden und ja.. ein das Plugin crasht beim beenden des VDR’s noch.. wird noch ein
 wenig dauern, bis ich Tester brauche und meine Quellen in den SVN auf sourceforge hochladen werde.

Stay tuned
