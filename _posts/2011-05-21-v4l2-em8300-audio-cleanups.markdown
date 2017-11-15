---
layout: post
title: v4l2-em8300 - Audio Cleanups
date: '2011-05-21 20:27:15'
---


Hier wieder ein Lebenszeichen vom v4l2-em8300 Projekt.

Ich habe die letzten zwei Tage genützt um den Audio Teil des Treibers ein wenig aufzuräumen. Ab jetzt wird nur noch ALSA unterstützt und alle Moduloptionen bezüglich
 Audio wurden entfernt. Langsam aber sicher habe ich schon viele Teile aufgeräumt und der
 Treiber wird immer besser 🙂

Über die nächsten Schritte in der Entwicklung bin ich mir noch nicht sicher. vbuf2 wäre sicherlich eine Überlegung wert, da ich möglichst viel Kernel-Funktionalität verwenden möchte – macht den Treiber schön klein und übersichtlich. Ich hoffe ich werde in den nächsten Wochen/Monaten wieder einmal Richtig viel Zeit fürs hacken haben.

Achja – Sourcen gibts [hier.](https://github.com/austriancoder/v4l2-em8300)
