---
layout: post
title: 'Audio device: nVidia Corporation MCP61 High Definition Audio (rev a2)'
date: '2008-05-06 09:50:23'
tags:
- intel-hda
- mcp61
- nf61s-m2a
- rev-a2
- snd_hda_intel
---


Ich hatte gerade das Problem, dass die MCP61 rev a2 keinen Ton von sich gab. Es handelt sich dabei um ein **Biostar NF61S-M2A** Mainboard. Um nun die Onboard Soundkarte zur Kooperation zu bewegen, muss man einfach den **Intel HDA** Treiber verwenden und diese Zeilen in die **/etc/modprobe.conf** einfügen:

*options snd-hda-intel enable=1 index=0
 alias snd-card-0 snd-hda-intel
 options snd-hda-intel model=6stack*

Happy Hacking
