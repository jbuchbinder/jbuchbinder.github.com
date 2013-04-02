---
title: Ubuntu touchpad annoyance
author: jeff
layout: post
permalink: /2006/06/29/ubuntu-touchpad-annoyance/
categories:
  - Hacks
---
# 

After more than six months of dealing with the Synaptics touchpad driver interpreting my hand brushing against the pad as a “click”, I [found a small change][1] to xorg.conf which will take away the sting of using a touchpad with [Ubuntu][2]/[Kubuntu][3].

 [1]: http://ubuntu.wordpress.com/2006/03/24/disable-synaptics-touchpad/
 [2]: http://www.ubuntu.com
 [3]: http://www.kubuntu.org/

Simply add the following lines in **/etc/X11/xorg.conf** in the InputDevice clause for the touchpad, and restart X:  
`
        Option          "SHMConfig"             "on"
        Option          "MaxTapTime"            "0"
`

Just had to share that, it took me so long to get up the resolve to actually \*look\* for a solution …