---
title: remserial binary for NSLU2
author: jeff
layout: post
permalink: /2008/10/10/remserial-binary-for-nslu2/
categories:
  - Hacks
tags:
  - nslu2
---

For all those fans of the venerable [NSLU2][1] (or “slug” as we like to call it), I have another package for OpenSlug/BE. This time it’s [remserial][2], a Linux equivalent to the BSD “[netfwd][3]” software, allowing serial ports to be redirected over TCP.

 [1]: http://www.nslu2-linux.org/
 [2]: http://lpccomp.bc.ca/remserial/
 [3]: http://www.bsdua.org/netfwd.html

Package: [remserial\_0.2000-1\_armv5b.ipk][4]  
Source: [remserial.tar.gz][5]

 [4]: http://www.mediafire.com/?sznttmgdi2c
 [5]: http://www.mediafire.com/?nlwtzntt2jw

For those enterprising people who would like to use my [armv5b-softfloat-linux][6] cross compilation toolchain, I have made it available on [mediafire][7] as well. It was compiled with Ubuntu 8.04.1 i386, so that’s the safest bet to use for compilation. I had used the NSLU2 “master makefile” to build it, since the vanilla crosstool had provided me little in terms of usable toolchains for the NSLU2.

 [6]: http://www.mediafire.com/?nmmwztgj5it
 [7]: http://www.mediafire.com/
