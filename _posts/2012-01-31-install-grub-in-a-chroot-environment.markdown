---
layout: post
title: Install Grub in a chroot environment
date: '2012-01-31 12:53:40'
tags:
- uuid
- grub
---


Image you destroyed your MBR sector of your hard drive/flash device and you are not able to load grub. You can easily fix this issue from an other Linux based computer. Simply run the following commands:

- mount /dev/sda1 /mnt/
- mount -t proc none /mnt/proc
- mount -o bind /dev /mnt/dev
- chroot /mnt/ /bin/bash
- /usr/sbin/grub-install –recheck –no-floppy /dev/sda

With this routine it it is also possible to fix UUID problems.
