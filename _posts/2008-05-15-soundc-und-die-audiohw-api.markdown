---
layout: post
title: sound.c und die audiohw api
date: '2008-05-15 00:37:55'
---


In den letzten Tagen und Wochen war ich recht fleißig und habe weiter an der audiohw API gearbeitet. Mittlerweile ist es mir
 gelungen die ifdef-hell ein wenig zu säubern und den Code dadurch wesentlich übersichtlicher zu machen.
 In den nächsten Wochen möchte ich gerne folgende Punkte erledigen:

- Prüfen ob *audio_is_initialized* überhaupt benötigt wird
- Eine elegante Lösung für *set_prescaled_volume* finden (audiohw_set_volume(l, r))
- Einige Sainty-Checks einbauen, ob eine bestimmte AUDIOHW_CAPS Kombination ok ist
- *sound_val2phys* in die Audio-Codec Treiber auslagern
- Für die cutoff Funktionen eigene CAPS definieren und verwenden
- Support für 1.5 DB Schritte verbessern
- *sound_set_loudness* und Co in den mas35xx Treiber verschieben
- Den DSP für den Simulator verwenden

Es ist zwar eine lange Liste, doch ich bin nicht unter Zeitdruck 😉
