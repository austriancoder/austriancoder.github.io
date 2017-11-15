---
layout: post
title: VDR 1.7 Statusupdate [Upd]
date: '2009-12-05 21:49:17'
---


[41f0211ca48e2c5a5af1fe41f9af644012fe91c4](http://projects.vdr-developer.org/git/?p=vdr-plugin-dxr3.git;a=commitdiff;h=41f0211ca48e2c5a5af1fe41f9af644012fe91c4) – das ist der Commit der Audioprobleme mit VDR 1.7
 korrigiert. Noch gibt av_log eine Warnung aus:

> [mp3 @ 0x9e70a60]incorrect frame size

Diese kann ignoriert werden… die Ursache ist mir bekannt, doch ich bin mir noch nicht sicher, wie
 ich das am schönsten löse 🙂

**Update:**

Der Bug 169 ist nun mit Commit 961b570ff897b54beabdcb4c54e59049203ce10a gefixt.
