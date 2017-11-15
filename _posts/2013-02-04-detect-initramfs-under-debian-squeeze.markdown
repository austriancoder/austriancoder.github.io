---
layout: post
title: Detect initramfs under Debian squeeze
date: '2013-02-04 11:11:19'
---


I am looking for a way to detect If a initramfs was used during boot. And after some reboots
 and reading of init script of initramfs-tools I found this solution.

 #!/bin/bash if [ -e /dev/.initramfs ]; then echo YES else echo NO fi

This may not work under wheezy or any other working distribution. But that’s okay for now 🙂
