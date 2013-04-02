---
title: NSLU2 based load balancer
author: jeff
layout: post
permalink: /2008/04/30/nslu2-based-load-balancer/
categories:
  - Hacks
tags:
  - nslu2 loadbalancing
---
# 

Another day, another project …

A few days ago I put together an [NSLU2][1]-based load balancer using [haproxy][2] to do the load balancing.

 [1]: http://www.nslu2-linux.org/
 [2]: http://1wt.eu/articles/2006_lb/

If you don’t have an NSLU2, go get one. Those things are incredible, and ridiculously useful. I’m using OpenSlug/BE, but any distro is awesome on these things.

*Hint: It takes some manual hacking of the haproxy.conf file and the init script to get it working from the optware packages. Of course, you have to tune it for the application you’re running…*