---
layout: post
title: "Backing up Footage and Digital Negatives using Cheap Cloud Storage"
date: 2015-05-08 15:12:37 -0400
comments: true
description: Cheap backups for footage and digital negatives 
cover: http://cdn1.tekrevue.com/wp-content/uploads/2015/03/amazon-cloud-drive.jpg
categories: 
 - Cinematography
 - Photography
---

If you're like me, you churn out a pretty hefty load of both digital film negatives (camera RAW images) and film footage (RAW or ProRes for me, but you may use a different format). This has always posed an issue for backing up original footage and photographs.

<!-- more -->

## Local Backups

I've been using an eSATA dock and a series of relatively inexpensive hard drives to back up video footage, and an eSATA hardware RAID-1 setup for my photos. This is an okay solution for making sure that I have a copy "on hand" if I ever need to pull a piece of footage for a reel or a photograph because someone asks for a copy, but it's fraught with disadvantages.

 * **Redundancy**. For the photos, it's RAID-1, so I'm only going to have a single backup copy, and that copy exists within the same physical device -- so if I mis-write something or screw up something when I push another piece of data to the drive, I might lose my data.
 * **Time**. For the videos, I have to make two backups to two separate drives, otherwise I lose the benefit of mirrored redundancy.
 * **Cost**. Drives, even though they might seem cheap, aren't. They tend to hover around 80-150$ apiece for the 5400 RPM variety.
 * **I HATE WINDOWS**. My only Windows machine, which is a video editing machine (until Resolve's editing features are better, in which case I'll probably do everything from a nice Linux box, finally) has a strange issue where a confluence of GPT + NTFS + SATA + (hard drive over 2TB) ends up truncating the disk partition table periodically and corrupting anything I put on the drive. I have to transfer the files via gigabit ethernet and CIFS/SMB to a saner operating system (Linux, FTW) and write them using ext4, HFS+ (unjournaled, of course), or NTFS -- depending on the level of compatibiity I want in a resore. This will probably go away when I move to a SAN, but it hasn't happened yet.
 
## Cloud Backups

Storing things in "the cloud" (essentially named for the part of the networking diagram of which you know nothing of the internals) seemed like a great idea -- but ongoing storage is *expensive*. Dropbox gets really expensive past 100GB, and Google seemed like they were going to offer some sort of unlimited solution, but it hasn't materialized yet. Hell, if you wanted to push to Amazon's S3 service, you were still looking at a pretty hefty monthly bill for the amount of data I was looking at pushing up.

## Amazon Cloud Drive

As of April-May 2015, [Amazon Cloud Drive](https://www.amazon.com/clouddrive/home/) started to offer an "unlimited" file tier for 60$/year. This seemed *way* too good to be true, so I did a quick "back of the napkin" calculation to figure out how much data I'd have to store there for it to be less expensive than S3.

Turns out that 208 GB is the magic number ; if I were to store that much data there for a year, it would cost me the same amount as S3's reduced redundancy storage -- about 5$/mo. As I'm looking at pushing many, many terabytes of information around, this immediately struck me as a great idea.

One of the downsides of Amazon Cloud Drive is that their clients are, for lack of a better word, absolute dogfood. They have a web interface, which is nice for browsing files, but there's nothing to perform syncing.

## acd_cli

Enter [acd_cli](https://github.com/yadayada/acd_cli) -- an opensource Python client which boasts the ability to synchronize large directories and files with a command line interface.

I've only been using it from a Linux box, but it has worked exceptionally well to sync large swaths of files up to Amazon's service. The syncing process can take a pretty long time, depending on your upstream bandwidth, so it's a good idea to start it going and leave it going, especially while you're not around.

## Confidential / Private Files

I don't know if you have any of these, but I tend to have plenty of financial documents, etc, which I'd rather not be directly accessible by whichever person / corporate entity is holding on to my files.

The solution I found -- opensource/free, of course -- is [Cryptomator](https://cryptomator.org/). It offers transparent encryption of filenames, padding of file sizes, and transparent encryption of the content themselves for any file/directory in a certain directory structure. You may not *have* to use it, but it's always nice to know that someone thought to put it together. 

## Other features

Amazon Cloud Drive also provides the ability to share files directly from its web interface -- but I haven't had cause to use it, since I still use Google Drive and other services to share files with people. Still, it's a nice feature to have, and hopefully it will mature in the coming months/years.

## Why not any of the alternatives?

Beyond cost, it comes down to *accessibility* and *fine print* for me. Backblaze's backup service, for example, relies on the idea that a single machine with a single drive can be backed up for 5$/month (60$/year) -- which wouldn't work for the myriad backup drives and shifting on-workstation content which defines a video or photo editing workstation. As far as accessibility goes, Amazon Cloud Drive is workable from my Linux machine as easily as it is from my Windows workstation (or, heaven forfend, a machine from the Cult of the Bitten Fruit) -- and I can put together my own client(s) if I find something lacking in the generally available ones.
