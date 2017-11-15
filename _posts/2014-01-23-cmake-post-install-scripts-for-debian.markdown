---
layout: post
title: 'CMake: Post install scripts for debian'
date: '2014-01-23 07:49:09'
tags:
- debian-2
- cmake
- postinst
---


I am using cmake during my job to create Debian installation packages for different kind of software projects. Today I run into an issue. I needed to run some post installation steps. I know that this is quite easy possible within a deb file, but how to archive the same with cmake?

It turned out to be quite easy:

<div class="oembed-gist"><script src="https://gist.github.com/austriancoder/1c3ba1d383fefbf8dd7fe773cebd882d.js"></script><noscript>View the code on [Gist](https://gist.github.com/austriancoder/1c3ba1d383fefbf8dd7fe773cebd882d).</noscript></div>Where postinst is the script which gets executed after the deb got installed.
