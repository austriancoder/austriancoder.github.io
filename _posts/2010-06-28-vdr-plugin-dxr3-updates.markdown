---
layout: post
title: vdr-plugin-dxr3 updates
date: '2010-06-28 14:10:13'
tags:
- alsa
---


In letzter Zeit hat sich wieder ein wenig was beim Plugin getan. Die OSS Ausgabe wurde nun entfernt um sich ganz der Audioausgabe mittles ALSA zu widmen. Leider gibt es in diesem Bereich
 noch ein paar kleinere Probleme, doch ich hoffe diese noch in den Griff zu bekommen. Das Wechseln des Kanales geht nun ohne gröbere Probleme (ALSA spinnt hin und wieder noch) und das Plugin kompiliert auch mit ffmpeg 0.6.

Auf meiner TODO findet sich im Moment folgendes:

- AC3-Support für ALSA
- ALSA Bugfixing
- StillPicture
- die letzten Sync-Probleme lösen

Es wird dann nicht mehr lange gehen, bis ich den buffer-sync-rewrite branch in den trunk mergen werde und dann sollte endlich ein neues langerwartetes Release folgen.

BTW: Es ist zu empfehlen einen modifizierten Treiber für die dxr3 zu verwenden, welchen es hier gibt: [hg.assembla.com/em8300-cgmeiner](http://hg.assembla.com/em8300-cgmeiner)
