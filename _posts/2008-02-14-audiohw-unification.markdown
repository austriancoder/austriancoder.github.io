---
layout: post
title: AudioHw Unification
date: '2008-02-14 15:40:09'
---


Im Moment nutze ich meine Freizeit um die AudioHw-Schicht in Rockbox ein wenig aufzuräumen und v.a. firmware/sound.c aufzuräumen und zu vereinfachen.

Hier einmal die großen Ziele von diesem Projekt:

- Eigener Audio-Treiber für die zwei Mas-Codec
- Einfache Möglichkeit um für ein Codec zu definieren was es alles in Hardware machen kann
 Z.b.: Bass, Prescaler,…
- Einheitliches Interface um die Lautstärke zu regulieren –> audiohw_set_volume(l, r)
- Preinit/Postinit aufräume

Eine sehr große Liste, doch sollte machbar sein. Ich freue mich schon auf ein paar Stunden Programmierarbeit.
