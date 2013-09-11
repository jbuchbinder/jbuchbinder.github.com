---
title: WRT54G Multiple External IP Trick
author: jeff
layout: post
permalink: /2006/07/31/wrt54g-multiple-external-ip-trick/
categories:
  - Hacks
---

To assign multiple external IP addresses to a WRT54G/S, you have to push a multiline variable into the `rc_firewall` nvram variable (non-volatile ram):

```
 nvram set rc_firewall="
 iptables -t nat -I PREROUTING -d x.y.z.1 -j DNAT --to-destination 192.168.1.x
 iptables -t nat -I PREROUTING -d x.y.z.2 -j DNAT --to-destination 192.168.1.x
 "
 nvram commit
```

This will protect the changes against being lost when the router is reset.

