---
layout: post
title: Octave 2.9 mit Gentoo
date: '2007-10-07 19:12:50'
---


Leider ist das offizielle Portage nicht immer up2date (**sci-mathematics/octave-2.1.73-r2**) und aus diesem Grund hier nun der einfachste Weg zu octave 2.9 unter Gentoo.

1. *# emerge layman*
2. *# layman -a science*
3. *# echo “source /usr/portage/local/layman/make.conf” >> /etc/make.conf*
4. *# emerge -av octave*

These are the packages that would be merged, in order:

Calculating dependencies… done!
 [ebuild N ] app-admin/eselect-blas-0.1 0 kB
 [ebuild N ] sci-mathematics/glpk-4.22 USE=”-doc” 1,385 kB
 [ebuild N ] app-admin/eselect-lapack-0.1 0 kB
 [ebuild N ] dev-tcltk/expect-5.43.0 USE=”X -doc” 514 kB
 [ebuild N ] dev-util/gperf-3.0.3 845 kB
 [ebuild N ] sci-libs/blas-reference-20070226 USE=”-debug -doc” 5,208 kB
 [ebuild N ] dev-util/dejagnu-1.4.4-r1 USE=”-doc” 1,056 kB
 [ebuild N ] virtual/blas-1.0 0 kB [1]
 [ebuild N ] sci-libs/lapack-reference-3.1.1-r1 USE=”-debug -doc” 0 kB
 [ebuild N ] virtual/lapack-1.0 0 kB [1]
 [ebuild N ] **sci-mathematics/octave-2.9.14** USE=”readline -curl -debug -doc -emacs -hdf5 -zlib” 9,185 kB [1]

Total: 11 packages (11 new), Size of downloads: 18,190 kB
 Portage tree and overlays:
 [0] /usr/portage
 [1] /usr/portage/local/layman/science

Would you like to merge these packages? [Yes/No]
