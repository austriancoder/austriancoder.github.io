---
layout: post
title: systemd on a Gentoo based system
date: '2013-01-21 21:03:26'
tags:
- systemd
---


I always wanted to try out systemd as I like the ideas and concept behind it. So lets get started:

- <span style="line-height: 15px;">add systemd USE-flag</span>
- emerge –ask –changed-use –deep @world
- emerge –ask systemd
- change grub config to use init=/usr/bin/systemd
- reboot

 localhost christian # systemd-analyze Traceback (most recent call last): File "/usr/bin/systemd-analyze", line 23, in <module> from gi.repository import Gio ImportError: No module named gi.repository

This can be fixed with:

 # emerge -av dev-python/pygobject

Here are the first results:

 localhost christian # systemd-analyze Startup finished in 2352ms (kernel) + 90695ms (userspace) = 93048ms localhost christian # systemd-analyze blame 3567ms NetworkManager.service 1311ms systemd-logind.service 530ms tmp.mount 528ms systemd-udevd.service 519ms systemd-vconsole-setup.service 393ms systemd-udev-trigger.service 363ms polkit.service 352ms sys-kernel-debug.mount 338ms dev-mqueue.mount 321ms dev-hugepages.mount 300ms boot-efi.mount 222ms systemd-sysctl.service 149ms systemd-user-sessions.service 114ms systemd-tmpfiles-setup.service 88ms console-kit-log-system-start.service 73ms console-kit-daemon.service 49ms dev-sda1.swap 44ms upower.service 33ms systemd-remount-fs.service

So my system boots 🙂 Lets see what is left to replace openrc.
