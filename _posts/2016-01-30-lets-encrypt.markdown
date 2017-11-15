---
layout: post
title: Let’s Encrypt
date: '2016-01-30 21:58:00'
tags:
- lets-encrypt
- startssl
---


As HTTPS is a must nowadays I decided a year a go to give it a try and got a certificate from [startssl](https://www.startssl.com/). The process at startssl took quite some time and was not that easy. With [lets encrypt](https://letsencrypt.org) everything should be much easier and faster to setup – lets give it a try @[ueberspace](https://uberspace.de/) (my hoster).

There is a very good (German) [tutorial directly from ueberspace](https://funkenstrahlen.de/blog/2015/12/19/lets-encrypt-auf-uberspace/) for the whole process. Two minutes later everything was done and it worked! There is only one missing part. As the generated certificate is only valid for 90 days I created a little script which gets run every month – thanks to cron.

<div class="oembed-gist"><script src="https://gist.github.com/austriancoder/911ca10c26dd24ac6b585ad4a62242a6.js"></script><noscript>View the code on [Gist](https://gist.github.com/austriancoder/911ca10c26dd24ac6b585ad4a62242a6).</noscript></div>
