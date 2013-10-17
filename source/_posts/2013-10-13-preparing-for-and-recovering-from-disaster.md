---
layout: post
title: "Preparing for and recovering from disaster"
date: 2013-10-13 20:01
comments: true
description: When things go wrong...
cover: 
categories: 
 - Photography
 - Cinematography
---

One of the greatest nightmares associated with digital cinematography and
photography is that of the specter of data loss. The very notion that your
carefully planned shots or footage could disappear in a single instant can
be Earth-shattering, since it may not be possible to reshoot (or may be
prohibitively expensive). The best defense is to be prepared, not only for
the possibility that you may lose data, but also to safeguard against that
possibility through preventitive measures.

## Preparation

There are a number of things you can do to try to protect against data loss,
both before and after shooting has taken place. Here are a few of them:

**Don't use dodgy or off-brand memory cards.** This may seem pretty obvious
to those who have been down this road, but really crappy cards tend to have
dodgy QA processes involved in their manufacture, so although you may get a
good card, you're just as likely to get a dud -- which could end up with your
data. I've found that "Amazon Basics" and "KomputerBay" cards have failed me
pretty regularly. Even "Transcend" cards have been pretty dodgy for me, on
occasion. I tend to stick with "SanDisk" branded cards, when I use SD media,
and there are a few decent manufacturers of CF media (Lexar, SanDisk, etc),
which tend to produce quality cards, in my experience.

**Storage media doesn't last forever.** Every piece of flash media has a
certain number of R/W cycles before it becomes unstable and/or unusable.
After a period of time, you might want to start regularly replacing your
media cards to avoid the possibility that errors will begin to occur. It's
also a good idea to low-level format the cards in between uses, which
supposedly increases their lifespan.

**A single physical copy of your product is a bad idea.** If you just move
files off to your laptop harddrive, you're practically expecting something
to destroy your media. A single SSD or spinning platter in a laptop is a
prime target for an accident to wipe out your data. Ideally, a RAID
(*R*edundant *A*rray of *I*nexpensive *D*isks) array would provide a
good tradeoff between inexpensive media and redundant storage. I built a
pretty inexpensive one with the following components:

 * [Sans Digital MR2UT+ MobileRAID](http://amzn.to/19EmtYA): A two-disk
   enclosure, which, when set to RAID-1, gives you a set of mirrored
   hard disks, accessible by USB 3.0 or an eSATA interface.
 * [Seagate Barracuda 2 TB HDD](http://amzn.to/19IlAdp): Two of these
   disks will provide you with a total of 2 TB of redundant storage.

**A single physical location is a bad idea.** Consider off-site backup. If
you don't have the money to store your data in [S3](http://aws.amazon.com/s3/)
or a similar service, consider using something like
[Bittorrent Sync](http://labs.bittorrent.com/experiments/sync.html), with a
friend or two providing remote backup locations. If this isn't feasible,
periodically backing up to [DLT](http://en.wikipedia.org/wiki/Digital_Linear_Tape)
or another backup tape, then storing that offsite, may be useful. If you
are questioning "why do I need off-site backup", just remember that a single
fire or natural disaster can destroy all of your hard work...

**Camera-based writing solutions.** Certain cameras (the Canon EOS 5D
Mark III, for example) have multiple media card slots, and have the ability
to write multiple copies of the same media. This can help circumvent the
tragic circumstance (to which I have fallen victim) of a completed shoot
with the inability to read any of the captured data later on. To understand
this, [read more here](http://protogtech.com/cameras/canon-5d-mark-iii-record-separately-vs-record-to-multiple-performance-comparison/).
It should be noted that there are some performance limitations to this,
but if you're not shooting RAW video and your camera body can handle this,
you might want to seriously consider it.

## Recovery

There is a pantheon of free and open-source software suites which provide
recovery of lost files, deleted files, destroyed partitions, etc. The true
nightmare scenario would involve a piece of damaged media, from which the
data cannot be extracted -- but never assume this unless you have exhausted
all other avenues of recovery.

 * [PhotoRec/Testdisk](http://www.cgsecurity.org/wiki/PhotoRec) (Open source,
   Linux/Windows/Mac/DOS/etc). This is one of my favorites, although it
   may potentially require some fairly in-depth technical expertise to
   fully exploit its potential.
 * [Recuva](http://www.piriform.com/recuva) (Freeware, Windows). Recovers
   deleted files.
 * [Hiren's Boot CD](http://www.hirensbootcd.org) (Freeware, Boot Disc).
   Hiren's is a classic recovery and utility boot disk, which can be
   booted on any Intel-based computer. The download is free, and it has
   a very comprehensive suite of recovery tools. If you don't have a copy
   of this disc hanging around your studio or house -- why not?
 * [Wondershare Photo Recovery](http://www.wondershare.com/disk-utility/cr2-photo-recovery.html) (Freeware, Windows/Mac).
   A semi-commercial digital media file recovery suite.
 * [iCare Recovery Free](http://www.icare-recovery.com/free/camera-raw-photo-recovery-free.html) (Trialware, Windows).
   This has a 2GB maximum data file recovery limit with the trial, otherwise
   a license has to be purchased.
 * [saveimg](https://homes.cs.washington.edu/~oskin/saveimg.html) (Opensource, Linux/Mac).
   Extracts JPEG images from raw disk devices. Requires some expert
   knowledge to use properly.
 * [Foremost](http://foremost.sourceforge.net/) (Opensource, Linux/Mac).
   Digital forensic tool to recover files based on headers, footers, and
   internal data structures.
 * [SanDisk RescuePRO](http://www.lc-tech.com/pc/sandisk-rescuepro-and-rescuepro-deluxe/) (Trialware, Windows).
   SanDisk's recommended recovery software.
 * [ddrescue](http://www.gnu.org/software/ddrescue/ddrescue.html) (Opensource, Linux/Mac).
   A data recovery tool. It copies data from one file or block device
   (hard disc, cdrom, etc) to another, trying hard to rescue data in case
   of read errors.
 * [Stellar Photo Recovery](http://www.stellarphotorecoverysoftware.com/camera-recovery/) (Trialware, Windows/Mac).
   Another digital photo recovery suite. The trialware shows what can be
   recovered, with previews.
 * [PC Inspector](http://www.pcinspector.de/default.htm?language=1) (Freeware, Windows).
 * [DataRescue](http://www.prosofteng.com/products/data_rescue.php) (Mac).
 * [Camera Salvage](http://subrosasoft.com/OSXSoftware/index.php?main_page=product_info&cPath=1&products_id=3) (Freeware, Windows).
 * [PhotoRescue](http://datarescue.com/) (Windows/Mac).
 * [CF Card Recovery](http://www.cfcardrecovery.com/) (Trialware, Windows/Mac).

Hopefully, this will either make it easier to avoid potential data loss, or
at least help to minimize the impact, if and when you end up losing data.

As always, good luck!

