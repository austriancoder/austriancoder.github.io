---
layout: post
title: device-tree introspection
date: '2017-09-20 19:13:01'
---

From time to time I need to inspect a used device-tree of a running device. For instance, the used bootloader (u-boot, barebox, ...) patches the the initial specified dtb and I want to see the modified one. All that is needed is an installed device-tree-compiler on the target.

```bash
$ dtc -I fs -O dts /sys/firmware/devicetree/base
```
