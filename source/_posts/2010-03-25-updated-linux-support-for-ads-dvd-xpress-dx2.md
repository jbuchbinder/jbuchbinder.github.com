---
title: 'Updated: Linux support for ADS DVD Xpress DX2'
author: jeff
layout: post
permalink: /2010/03/25/updated-linux-support-for-ads-dvd-xpress-dx2/
categories:
  - Development
  - Hacks
---

In 2007, I had posted a patch for the [ADS DVD Xpress DX2][1] device to work on Linux, but it had been based on an antiquated kernel version, etc.

 [1]: http://www.adstech.com/products/USBAV-709-EF/intro/USBAV-709_intro.asp?pid=USBAV-709-EF

Since then, [someone][2] was nice enough to post an updated version of the driver, but without DVD Xpress DX2 support. I put together a patch which ensures that the drivers now compile and use the new I2C and V4L2 APIs. I can’t guarantee that it works, only that it compiles the driver properly now. Theoretically it should work, but I can’t find my DVD Xpress DX2 to try out the hardware properly.

 [2]: http://go7007.imploder.org/

* Original driver :   
* Patch : [wis-go7007-linux-098-5-20100325.diff](/images/2010/03/wis-go7007-linux-098-5-20100325.diff)

