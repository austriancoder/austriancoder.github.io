---
layout: post
title: 'checking for XML::Parser... configure: error: XML::Parser perl module...'
date: '2008-02-14 12:21:14'
---


 is equired for intltool.

Dieser Fehler bekam ich bei einem Update des NetworkManager’s unter Gentoo. Scheinbar ist hängt dies mit Perl, intltool und dem xml parser zusammen. Für mehr Informationen einfach einen Blick auf [https://bugs.gentoo.org/show_bug.cgi?id=41124](https://bugs.gentoo.org/show_bug.cgi?id=41124 "Gentoo Bugs")

Und hier nun die sehr einfache Lösung – works for me(tm)

*emerge  XML-Parser networkmanger*

Happy Hacking..
