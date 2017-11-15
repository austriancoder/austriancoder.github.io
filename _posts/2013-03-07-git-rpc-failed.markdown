---
layout: post
title: 'git: RPC failed; result=22, HTTP code = 504'
date: '2013-03-07 15:44:38'
tags:
- git
---


 git clone http://review.coreboot.org/p/coreboot.git coreboot Cloning into 'coreboot'... error: RPC failed; result=22, HTTP code = 504 fatal: The remote end hung up unexpectedly

The error occurs in ‘libcurl’, which is the underlying protocol for http. To get more details about the error, set GIT_CURL_VERBOSE=1
