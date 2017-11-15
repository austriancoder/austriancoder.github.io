---
layout: post
title: Vivante meets devicetree
date: '2014-05-24 23:41:14'
tags:
- devicetree
- dts
- gpu
- vivante
- etnaviv
---


It took me some time to rework the device tree bindings but it looks like it starts to work!

<div class="oembed-gist"><script src="https://gist.github.com/austriancoder/6196fa33011a120a01dd54dbd077a60d.js"></script><noscript>View the code on [Gist](https://gist.github.com/austriancoder/6196fa33011a120a01dd54dbd077a60d).</noscript></div>Gets loaded into :

[ 3.358155] vivante: module is from the staging directory, the quality is unknown, you have been warned.
 [ 3.373087] imx-sgtl5000 sound.15: sgtl5000 2028000.ssi mapping ok
 [ 3.379150] [drm] add child gpu2d
 [ 3.379154] [drm] add child gpu3d
 [ 3.380395] vivante-gpu 134000.gpu2d: pre gpu[idx]: 0x00000000
 [ 3.380401] vivante-gpu 134000.gpu2d: adding core @idx 1
 [ 3.380408] vivante-gpu 134000.gpu2d: post gpu[idx]: 0xecb56c10
 [ 3.380460] vivante gpu-subsystem.11: bound 134000.gpu2d (ops gpu_ops [vivante])
 [ 3.380467] vivante-gpu 130000.gpu3d: pre gpu[idx]: 0x00000000
 [ 3.380473] vivante-gpu 130000.gpu3d: adding core @idx 0
 [ 3.380479] vivante-gpu 130000.gpu3d: post gpu[idx]: 0xecb57210
 [ 3.380502] vivante gpu-subsystem.11: bound 130000.gpu3d (ops gpu_ops [vivante])
 [ 3.380533] IO:R f0200018 14010000
 [ 3.380537] IO:R f0200020 00002000
 [ 3.380540] IO:R f0200024 00005108
 [ 3.380546] vivante gpu-subsystem.11: model: 2000
 [ 3.380551] vivante gpu-subsystem.11: revision: 5108
 [ 3.380554] IO:R f020001c e0296cad
 [ 3.380558] IO:R f0200034 c9799eff
 [ 3.380561] IO:R f0200074 2efbf2d9
 [ 3.380564] IO:R f0200084 00000000
 [ 3.380567] IO:R f0200088 00000000
 [ 3.380572] vivante gpu-subsystem.11: minor_features: c9799eff
 [ 3.380578] vivante gpu-subsystem.11: minor_features1: 2efbf2d9
 [ 3.380583] vivante gpu-subsystem.11: minor_features2: 0
 [ 3.380588] vivante gpu-subsystem.11: minor_features3: 0
 [ 3.380592] IO:R f0200000 00070100
 [ 3.408629] IO:R f0200004 7fffffff
 [ 3.408632] IO:R f0200000 00070100
 [ 3.412940] vivante gpu-subsystem.11: 130000.gpu3d: using IOMMU
 [ 3.413080] IO:R f01f8018 14010000
 [ 3.413083] IO:R f01f8020 00000320
 [ 3.413087] IO:R f01f8024 00005007
 [ 3.413093] vivante gpu-subsystem.11: model: 320
 [ 3.413098] vivante gpu-subsystem.11: revision: 5007
 [ 3.413101] IO:R f01f801c e02c7eca
 [ 3.413105] IO:R f01f8034 c1399eff
 [ 3.413108] IO:R f01f8074 020fb2db
 [ 3.413111] IO:R f01f8084 00000000
 [ 3.413114] IO:R f01f8088 00000000
 [ 3.413120] vivante gpu-subsystem.11: minor_features: c1399eff
 [ 3.413126] vivante gpu-subsystem.11: minor_features1: 20fb2db
 [ 3.413131] vivante gpu-subsystem.11: minor_features2: 0
 [ 3.413136] vivante gpu-subsystem.11: minor_features3: 0
 [ 3.413139] IO:R f01f8000 00070100
 [ 3.438615] IO:R f01f8004 7fffffff
 [ 3.438619] IO:R f01f8000 00070100
 [ 3.442583] vivante gpu-subsystem.11: 134000.gpu2d: using IOMMU
 [ 3.442681] [drm] Initialized vivante 1.0.0 20130625 on minor 1
