---
layout: post
title: "BMPC4K Workflow with Premiere and Resolve"
date: 2014-05-08 07:05:17 -0400
comments: true
description: Overview of my basic Premiere/Resolve workflow
cover: /images/davinci-resolve.jpg
categories: 
 - Cinematography
---

There are a number of "accepted" workflows for going between Adobe Premiere
(as an NLE) and Davinci Resolve (for color correction/grading) for BMPC4K
footage. I am going to detail the workflow I have been using, which should
be useful both for the BMPC4K camera, as well as the BMPCC and BMCC cameras.

1. **Preparation**. Make sure your camera is producing footage at the 23.98
   fps frame rate, rather than 24 fps. "True" 24 fps is not quite the same
   thing as the "24P" frame rate we are used to.

1. **Load your media onto your workstation**.

1. **Create simple proxies**. Using
   [prores-proxies](https://github.com/shootthemoonfilms/prores-proxies),
   create "cheap" lower quality proxies encoded using the H.264 codec in
   Quicktime files. I have been experimenting with using the ".mpg"
   extension to [force Premiere to use its own internal Quicktime decoder](http://blogs.adobe.com/VideoRoad/2012/12/premiere-pro-and-quicktime-and-nikon-oh-my.html),
   rather than the relatively dodgy external one, but the basic process
   is the same.

1. **Edit**. Using the proxy files, edit your footage in Premiere. You do
   not have to bother with any fancy transitions or effects yet -- just
   perform a basic edit.

1. **Export to Resolve**. Export a "Final Cut Pro XML" file, using the
   File &gt; Export menu option.

1. **Create a new Resolve Project**. Open Resolve, and create a new project.
   Import the original files (not the proxies) into your media pool.

1. **Import the XML from Premiere**. Import the "Final Cut Pro XML" export,
   with "Automatically import source clips into pool" deselected. This last
   part is very important, as it forces Resolve to use the clips you already
   have in the Media Pool.

1. **Color Grade**. Perform your color grade in Resolve.

1. **Export**. In the "Delivery" tab, select the whole timeline, choose
   "Easy Setup",and select  "Final Cut Pro XML Round-Trip". Change any options
   here to your liking.

1. **Import Roundtrip XML in Premiere**. Import the Round-Trip XML file in
   Premiere. This will bring in all of the graded footage.

1. **Perform the remainder of your edits**. Tweak your footage, copy or
   create your title cards, etc.

*This is a very basic overview of my current BMPC4K + Resolve + Premiere
workflow right now, and it may change.*

