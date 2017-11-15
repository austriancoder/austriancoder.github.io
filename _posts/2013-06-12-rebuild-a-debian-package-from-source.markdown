---
layout: post
title: Rebuild a Debian package from source
date: '2013-06-12 10:49:25'
tags:
- dpkg-buildpackage
- dpkg
- ntpd
---


In some rare cases I need to debug some networking protocols and my target of interest
 is NTP. I am debugging an issue where (maybe) NTP sets the current time backwards about
 two hours. My first candidate to look deeper is ntpd.

But what do I see… debugging option is disabled in the Debian squeeze package of ntp.
 WTF?! – the only nice way to do useful debugging without wireshark. The good thing is
 that Ubuntu had the same miss-configuration and got it [fixed](https://bugs.launchpad.net/ubuntu/+source/ntp/+bug/47683).

So I only need to rebuild the ntpd package with debugging enabled.


# sudo apt-get build-dep ntpd
# sudo apt-get source ntpd
# cd ntp-4.2.6.p2+dfsg
# nano debian/rules
# dpkg-buildpackage -rfakeroot -uc -b
The result is a deb in the parent folder.
