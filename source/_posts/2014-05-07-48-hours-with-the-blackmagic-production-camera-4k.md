---
layout: post
title: "48 Hours with the Blackmagic Production Camera 4K"
date: 2014-05-07 13:45:23 -0400
comments: true
description: 
cover: /images/2014-boston-48hr-festival.jpg
categories: 
 - Cinematography
 - Film
 - Post-Mortem
---

This year, my team ([Shoot the Moon Films](http://www.shootthemoonfilms.com)),
entered the 2014 [Boston 48 Hour Film Festival](http://48hourfilm.com/en/boston/)
for the first time. It's an interesting experience, going from genre and
parameters to fully formed script, to planning and preproduction, to
shooting and execution, to editing, scoring, grading, and full post-production
in a single weekend. I've learned a lot about working with the 
[BMPC4K](http://www.blackmagicdesign.com/products/blackmagicproductioncamera4k)
camera in that time. I am going to iterate over some of the more important
things that I learned over the weekend.

## Overheating

This simply did not happen. I had heard some horror stories about the camera
body breaking or overheating after long periods of filming, but even in 
direct sunlight for significant periods of time, I did not find this to be
the case. My EOS body used to overheat more than this one...

## ND filters

My Tiffen 77VND was indispensible. If I didn't have that single piece of
equipment, every exterior shot would have been very, very different. I wanted
a medium DOF and a standard shutter rate for my exterior shots -- which meant
that the sunlight had to be stopped down. The variable ND filter delivered
perfectly.

## EVF

The Cineroid was a life-saver. I do not think I would have done as well
without its superior focus-peaking, crop indications, etc. The only feature
sorely missing from the EVF4CSS is waveforms/scopes, which would have been
a bit more useful than eyeballing the full extent of the dynamic range.

## V-mount batteries

If you are not turning your camera off between takes, you are going to need
more than one battery for a day-long shoot. Do **NOT** skimp on a V-mount
battery charger. They take a very long time to trickle charge, so make sure
you have a rapid charger. Also, spares. They may be expensive, but having to
wait on a battery charging could blow a shoot.

## Audio

This is less a "thing" with the BMPC4K body, and more of a general observation.
You cannot skimp on sound. You just *can't*. You can always rely entirely on
tight OTS shots and other closeups and use on-camera mics, but it shuts off
an entire avenue of creative wider shots. A boom operator is *not* just your
buddy holding a mic on a pole -- they need to know what they are doing,
otherwise you could be pushing very substandard audio into post-production.
Especially on a tight time limit, this can make the difference between making
a deadline, or having truly horrendous sound.

Also, get a really competent audio engineer. Preferably a really anal-retentive
one with an insane attention to detail. Even if you have perfect video, really
crappy audio can break the illusion of your film. **DO NOT SKIMP**. SERIOUSLY.

## That PA or AD -- you need them more than you think

If someone is not taking copious shot notes, you are going to find yourself
up at some ungodly hour, digging through footage for that shot that you
*know* you got. Save yourself the trouble, and have someone taking care of
all of that.

## Proxy files

I used a new method of creating intermediate proxy files for editing, since
Premiere was not very cooperative in directly loading the Prores files from
the camera. *I made my code public in a project called
[prores-proxies](https://github.com/shootthemoonfilms/prores-proxies).* This
little trick made sure that, instead of having to render all of my footage
out at the Davinci Resolve speed of 3-6 fps (on my non-Red-Rocket workstation),
I was able to render it to proxies at about full speed (which was about 24fps).
Without this, I wouldn't have been able to edit the footage without several
footage drops during the day -- if at all -- during the limited timeframe I
had to do so.

## Premiere Quicktime support on Windows is dog food

Something is wrong with it. I have no idea why, but the QT decoder decided
to "give up the ghost" quite a few times during editing. There is supposedly
a renaming hack, which allows the Premiere internal decoder to handle the
files, but I was not privvy to this information during editing. I will update
my documentation and/or author a post on this at some point in the near future,
as it is **VERY** irritating.

## Too many cooks

One person edits. Someone can *assist* them, but you need to have one editor, 
who makes the decisions as to what goes into your final product. If you try
to "edit by committee", you may end up with a very tired and frustrated primary
editor, and the possibility of some very incomprehensible footage.

If your editor and director are not the same person, the director sits in
with the editor to make decisions, where they need to be made. Ideally the
script notes, etc, provide enough information to the editor to perform his
job.

Also, do not get caught up in reviewing dailies if you are taking part in a
time-sensitive competition. This is a recipe for disaster.

## Coloring

Even shooting with 10-bit ProRes 422 HQ, the advantage over H.264 DSLR
footage is immediately apparent. There is a lot of latitude for coloring
and correction, which would simply not be possible with the same level of
output quality with H.264.

I ended up performing a manual grading (as in, no LUTs or presets) for the
project we did, and I am very satisfied with the end result.

## Grain

I love the "film grain" that the sensor on this camera produces. I am sure
that I have mentioned it in earlier posts, but it really does give that
organic film look to your output.

## Do not use services like Google Drive for your deliverables

They tend to like to really hurt you in upstream speeds -- only when you are
on serious deadline. A better alternative for large media files is to set up
[btsync](http://www.bittorrent.com/sync) on both sides, and transfer with far
more efficiency. You will be glad that you did it.

## Too many hats ... sink ships?

There is serious temptation to wear more than one hat. Hell, we all wear more
than one hat on most small sets. The issue comes when you end up wearing
three or four (director, cinematographer, editor, colorist), and realize that
you do not get to sleep until everything is "out the door". Delegate. Find
people who are good at this stuff, and let them do it. You do not have to be
good at everything, just find people who are.

## Conclusion

I had a good time -- but I could have been less stressed out, if I had known
some of this in advance.

