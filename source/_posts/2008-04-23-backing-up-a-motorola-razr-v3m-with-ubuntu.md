---
title: Backing up a Motorola RAZR v3m with Ubuntu
author: jeff
layout: post
permalink: /2008/04/23/backing-up-a-motorola-razr-v3m-with-ubuntu/
categories:
  - Hacks
---
# 

I’ve had a Sprint Motorola RAZR v3m for a while, and when the time came to move to a Blackberry (for work), getting the information off of it would have been a horrendous process.

Instead, I present a pretty simple way of doing this using the Subversion version of opensync’s sync-moto script. Note that I did this under Ubuntu 7.10 (Gutsy Gibbon):

• Get the id by using lsusb:  
$ **lsusb**  
Bus 005 Device 001: ID 0000:0000  
Bus 003 Device 001: ID 0000:0000  
Bus 002 Device 001: ID 0000:0000  
Bus 004 Device 003: ID 0483:2016 SGS Thomson Microelectronics Fingerprint Reader  
Bus 004 Device 002: ID 0a5c:2110 Broadcom Corp.  
Bus 004 Device 001: ID 0000:0000  
Bus 001 Device 003: ID 22b8:2a64 Motorola PCS  
Bus 001 Device 002: ID 046d:0a02 Logitech, Inc.  
Bus 001 Device 001: ID 0000:0000  
• Add the following definition under /etc/modprobe.d/somethingorother :  
**alias cdc_acm usbserial  
options vendor=0x22b8 product=0x2a64**  
• Plug in the phone and issue a:  
** sudo /sbin/modprobe cdc_acm vendor=0x22b8 product=0x2a64**  
• Download the Subversion copy of the opensync moto-sync plugin from:

https://svn.opensync.org/plugins/moto-sync/

• Issue the following sync command:  
**./mototool -d /dev/ttyUSB0 –backup –file mybackupfile.csv**