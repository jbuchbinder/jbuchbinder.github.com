---
layout: post
title: "Opensource Contact Sheets for Photographers"
date: 2016-02-08 15:37:08 -0500
comments: true
description: Creating contacts sheets using opensource software
cover: /images/2016/02/contact-sheet.jpg
cover_width: 740
cover_height: 592
categories: 
 - Photography
 - Hacks
---

One of the disadvantages to being a pretty active photographer is trying to handle archiving old shoots and being able to quickly locate a certain shot amongst thousands of directories of RAW stills, which may not be present on your local media. Enter the humble *contact sheet*.

<!-- more -->

Stretching all the way back to the days of Ansel Adams, the [contact sheet](https://en.wikipedia.org/wiki/Contact_print) has provided a simple way to view large numbers of prints at a glance. With the introduction of digital photography, software packages like [Picasa](https://picasa.google.com/) (and [iPhoto](http://www.apple.com/mac/iphoto/), for the followers of the Cult of the Bitten Fruit), have enabled large numbers of photos to be viewed at a glance -- however, they have the downside of needing the actual photos to be readily accessible (to one degree or another).

[My hack](https://gist.github.com/jbuchbinder/667efd7355f9c2da948a) is Linux-based, although it will work on any platform supporting [bash](https://www.gnu.org/software/bash/), [dcraw](https://www.cybercom.net/~dcoffin/dcraw/), and [ImageMagick](http://www.imagemagick.org/script/index.php)'s *montage* (along with *xargs*, *printf*, and a bunch of other bash extensions). It has the additional advantage of being able to resume from whenever it is stopped without losing or repeating work. I wrote it to support my layout, which involves a single directory full of timestamped unique directory names -- but it should work as long as the directory names are unique, regardless of the structure.

{% gist jbuchbinder/667efd7355f9c2da948a %}

