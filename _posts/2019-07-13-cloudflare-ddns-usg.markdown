---
layout: post
title: Cloudflare DDNS and Unifi USG
date: '2019-07-13 18:00:00'
tags:
- cloudflare
- unifi
- usg
---

This is a quick post for those of you looking for a completely free dynamic DNS solution for your home network running on Unifi.

For years, I was a happy [DynDns](https://dyn.com/dns) user and even paid once for a premium plan. But now it is time for a change as I recently switched to [Unfi](https://www.ui.com/) network equipment including a [USG](https://www.ui.com/unifi-routing/usg/). Currently, I am using [Cloudflare](https://cloudflare.com) for CDN, DDOS protection, free SSL certificates and DNS with a free account. Thankfully, Cloudflare has a free API that allows you to automatically update your DNS records.

### Preparation of the USG

The installed version of ddclient on the USG is too old to support Cloudflare's v4 API so we need to update it first.

<script src="https://gist.github.com/austriancoder/ceee29fd6e4ca091490bfd74f5d10e33.js"></script>

### Configure Cloudflare DDNS on the Controller

With Controller version 5.10.25.0 it is not possible to configure Cloudflare DDNS via the UI, so we need to go another route. Luckily, the config.gateway.json is a file that sits in the UniFi Controller filesystem and allows custom changes to the USG that aren't available in the web GUI. For more [information visit Unifi [documentation here](https://help.ubnt.com/hc/en-us/articles/215458888-UniFi-USG-Advanced-Configuration).

<script src="https://gist.github.com/austriancoder/4885d51580b76a38fd4d9b5256fb13c3.js"></script>

After this step was done we are almost ready. Finally, we need to run a "force provision" to the USG in the UniFi Controller Devices > USG > Config > Manage Device > Force provision. That's it!

Keep in mind that chances are quite high that you might need to reupdate ddclient on the USG after an Firmware update.
