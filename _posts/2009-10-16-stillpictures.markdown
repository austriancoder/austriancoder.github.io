---
layout: post
title: StillPictures
date: '2009-10-16 11:53:07'
---


Hallo,

endlich habe ich mich getraut, den alten SpuEncoder durch den neuen zu ersetzten, auch wenn es noch zu Problemen
 kommen kann. Doch dies war ein wichtiger Schritt in die richtige Richtung.

Bevor ich die bekannten Bugs im SpuEncoder behebe, brauche ich ein bisschen Abstand und von dieser Thematik und bin dabei die StillPicture-Methode zu fixen. Wie es sich herausstellt ist das Vorhaben – wie sollte es anders sein – nicht ganz trivial. Zu aller erst muss ich mich mit den verschiedenen Playmodes vertraut machen und da habe ich schon ein paar Dinge gefunden, die im Treiber nicht vorhanden sind. Ein Beispiel wäre hier  EM8300_PLAYMODE_SINGLESTEP. Ist zwar in der em8300.h vorhanden, wird aber vom Treiber nicht unterstützt.
 Das wird noch eine interessante Reise in das Land der em8300 werden. Es wäre schön, wenn es eine ordentlich dokumentierte API für die Treiber geben würde. Bin es aber eh schon gewohnt immer alles auszuprobieren zu müssen und nach 1-2 Tagen hackings eine Lösung zu finden.

greets
