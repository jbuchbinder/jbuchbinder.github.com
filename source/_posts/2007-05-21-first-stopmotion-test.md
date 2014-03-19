---
title: First stopmotion test
author: jeff
layout: post
permalink: /2007/05/21/first-stopmotion-test/
categories:
  - Photography
  - Video and Animation
---

Our first few stopmotion animation tests were successful. As per everything else we do, everything was done with Linux and freely available opensource software. In this case, [gphoto2][1], imagemagick and mplayer (with ffmpeg thrown in for the .flv conversion for [Gootube][2]. 

 [1]: http://gphoto.org
 [2]: http://www.youtube.com/

We used my Canon 350D mounted on a tripod with [Adam’s][3] fixed focal length 135mm lens, with fixed lighting and a green background for eventual [chromakeying][4]. There was a quick hack involved getting gphoto2 to immediately spit out a photo, instead of trying to logically process it, which was solved with:

 [3]: http://www.flickr.com/photos/grendelkhan/
 [4]: http://en.wikipedia.org/wiki/Chroma_key

`gphoto2 --set-config "Capture size class"="Full Image" --capture-preview --filename "${OUTPUTFILE}" --force-overwrite`

(If you choose to try this, remember that whatever format you set your camera to will be the format that it comes out in, so don’t set it to RAW unless you really don’t value your time and want to have to convert it using dcraw.) 

The first video can be viewed at .
