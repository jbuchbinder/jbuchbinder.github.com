---
title: PERC Controllers and Why Dell Needs a Kick in the Can
author: jeff
layout: post
permalink: /2008/09/12/perc-controllers-and-why-dell-needs-a-kick-in-the-can/
categories:
  - Hacks
---

This past week, I stumbled on a strange problem with Dell “PERC” RAID controllers in certain rackmount servers, where they would suddenly just stop working for no apparent reason. The nice people at Dell did actually have firmware available for the PERC 3 and 4 controllers to fix this problem, which was pretty nice.

The part that \*wasn’t\* nice was that they were some stupid [Windows][1] binaries which required a floppy disk to be inserted.

 [1]: http://www.eskimo.com/~webguy/writings/winsucks.html

First of all, who has a laptop with a floppy drive anymore, and second of all, what if you, like other sane people, don’t use Windows? Thirdly, how often does a floppy disk magically fail to work in a floppy drive?

I ended up doing the following:

*   Create a [VirtualBox][2] VM
*   Use `dd if=/dev/zero of=floppy.img bs=1k count=1440` to create a floppy image, which I mounted in the VirtualBox
*   “Format” the floppy image in the VM, because apparently Dell’s fuqtard utility can’t write an image to an unformatted disk.
*   Use the stupid utility to write the floppy image.
*   Use `mkisofs -pad -b floppy.img -R -o cd.iso floppy.img` to create a CD image

 [2]: http://www.virtualbox.org/

Dell, I hate you. Your laptops overheat and suck out loud, and your stupid Windows-only disks and defective RAID controllers bother me. I’m not buying any more of your hardware. You can subsidize Microsoft some other way.
