---
layout: post
title: "To post or not to post"
date: 2013-09-07 13:18
comments: true
categories: 
 - Photography
 - Cinematography
---

Even though a good portion of the work has been completed when you press the
shutter button, or stop rolling, since all of your planning and execution has
been completed, there's still a final step (or series of steps) to bring that
artistic effort to a presentable format.

Many people shoot with default (or very close to default) settings on their
camera or videocamera, and do simple "post production" by simply cropping or
cutting whatever comes out of their camera body. This is a very "purist" way
of going about shooting, but can also rob your end product of some of the
polish and slight adjustments which can take good pictures or footage and
make them into something extraordinary.

All of that being said, there's a limit to the types and amounts of post
production which can and should be used, much in the way that overproducing
a musical album can result in a homogenous and lifeless product, robbed of
the "soul" and variances which make it unique. You are the only person who
can decide how much, if any, post processing is right for your project or
other artistic endeavor.

**RAW versus JPEG/H.264**

With DSLR cameras being used for both photography and cinematography, there
are places where the "processing" aspect can be pushed off into the post
production process.

For photography, RAW format pictures can allow recovery past some of the
previously accepted limits of what would normally be considered lost or
unusable. Effectively, it allows you to make the decisions which are
normally pushed off on your camera's processor (the DIGIC processor(s),
for all of you Canon users). It adds an additional step to the
post-processing workflow, in that you'll need a piece of software like
[Adobe Lightroom][1] for Windows/Mac users, or if you're a Linux user like me,
[Raw Studio][2]. It also adds a significant amount of time to the
photographic post-processing workflow, in that there are a number of
additional parameters which can be adjusted, which would normally result
in image degradation, but can be adjusted in RAW images with little or no
deleterious effect. If you're a [Magic Lantern][3] user, you can also
experiment with "dual ISO" images, which can create images with enormous
dynamic range through sensor tricks -- but which adds an another step
before RAW processing, that of running a CR2HDR binary. (If you're
interested in trying this out, but don't want to compile a CR2HDR binary
for Windows or Linux, I have binaries available [here][4])

 [1]: http://www.adobe.com/products/photoshop-lightroom.html
 [2]: http://rawstudio.org/
 [3]: http://www.magiclantern.fm/
 [4]: https://bitbucket.org/rufustfirefly/magic-lantern/downloads

For cinematography, there's a lot more to think about. Magic Lantern users
of Canon 5Dmk3 models (and some others, as well) have the option of being
able to shoot RAW video with some very fast CF cards. This adds a pretty
substantial amount of post-processing steps *before* your NLE (non-linear
editor) of choice enters the picture. There are a pretty wide swath of
applications which now support the Magic Lantern RAW format, including
[RAWanizer][5], but your best bet is to get involved with the Magic
Lantern forum if you want to begin working with a RAW workflow. The other
serious disadvantage is storage space. Standard H.264 video, which is
shot by most DSLR camera bodies, has issues with some digital artifacts in
certain scenarios, as well as some dynamic range issues (some of which can
be made better by use of flat color profiles like [Cinestyle][6], but I'll
leave that for later) -- but it produces fairly compact files, even at
1080p/24p (1920x1080 24fps progressive) resolution. RAW data can take
upwards of a gigabyte of space every 15-20 seconds. Your storage media
and backup solutions have to be able to deal with that, so it's something
to seriously consider before deciding to move a project to work with that
format.

 [5]: http://www.magiclantern.fm/forum/index.php?action=printpage;topic=5557.0
 [6]: https://www.technicolorcinestyle.com/download/

**White Balance**

It used to be accepted that white balancing (determining where "true white"
lies in an image, compensating for varying light color temperatures) had to
be done "in camera", before shots were taken. There are a number of tools
which allow this to be done in post-processing.

Photographers can do this when shooting with RAW camera images very
simply, as most RAW image processors have a simple white balancing tool. It's
still possible to do this with processed JPEG images, but with the
potential for losing some image data. Depending on how comfortable you are
with straying from the "truest possible image", you can decide where you
feel comfortable dealing with white balancing.

Cinematographers have a pretty vast array of white balancing and color
correction plugins available for their NLE of choice. I'm most familiar with
Adobe Premiere, so I'd mention [Fast Color Corrector][7] and
[Red Giant Colorista II][8], both of which offer pretty decent white
balancing capabilities, among other things. If you're concerned about
render speed, Fast Color Corrector seems to win out against Colorista II,
but Colorista II has some additional parameters and capabilities which
far outstrip what FCC has to offer. There's also software like
[Adobe Speedgrade][9] and [Blackmagic Design Davinci Resolve][10], both
of which offer white balancing, color correction, and color grading
capabilities. There are a few threads [comparing the two of them][11].

 [7]: http://blogs.adobe.com/VideoRoad/2010/05/using_the_fast_color_corrector.html
 [8]: http://philipbloom.net/forum/threads/tutorial-color-grading-and-styling-with-colorista-ii.2528/
 [9]: http://tv.adobe.com/watch/learn-premiere-pro-cc/color-grading-premiere-pro-sequences-in-speedgrade/
 [10]: http://digitalfilms.wordpress.com/2013/02/02/davinci-resolve-workflows/
 [11]: http://forums.planet5d.com/threads/123505-Adobe-Speedgrade-vs-DaVinci-Resolve

The important distinction is whether or not you want to spend the time
to properly white balance your images or footage before you take pictures.
It's not always condusive to your shooting workflow to do so, and if this
is a factor, you should seriously consider some of the post-processing
options. It's obviously to your greatest advantage to have the most
accurate input images/footage to bring into your post-processing
workflow, but sometimes it's not pragmatic to take a completely purist
attitude in this regard.

**Exposure**

We've all been bitten by changing light conditions, unexpected events, or
incorrect metering producing images or footage which has exposure problems.
If you're shooting RAW (or using Magic Lantern's Dual ISO hack), this is
an ideal place to examine using post-processing to correct these issues.

We would all like to properly expose everything (unless we have a
particular artistic reason for doing otherwise, since in the art of
photography or cinematography, there are generally exceptions to every
rule, rules were made to be broken, etc), but taking a post-processing
detour to correct such things is generally preferable to re-arranging a
shoot.

**Special Effects**

I'm not a big fan of post-processing special effects, mainly because I 
am a proponent of the idea that it takes some of the artistry out of
pulling off those same effects "in camera". I do understand that there
are certain effects which would be either very difficult or downright
impossible to achieve without the use of computer generated effects --
but there's a lot of things which can be accomplished *without* that.

Lighting is something which I've seen done in post, which generally
baffles me. It's something which is pretty simple to execute properly,
given a little time and effort. Saving images or footage with issues
might be a good use for that, but it's probably not something I would
recommend doing for everyday editing and processing.

For example, having someone "eaten" by light can be accomplished for
a cinematographer, simply by adjusting the fill light to blow out the
whites, then opening the iris of the lens (using a focus pulling kit,
or just a spare hand, for the less equipment-heavy among us) to allow
the fill light to "eat" the remainder of the image. That can be done
without any specific post-processing.

**Flat Color Profiles**

This is pretty much for cinematographers, since photographers could
simply take RAW photos -- and cinematographers shooting RAW should
probably ignore this section, as well.

There are quite a few "flat color profiles" available for DSLR
(and other) bodies, such as the aforementioned Technicolor Cinestyle
profile and the [Flaat Picture Style][12]. These work by effectively
increasing the dynamic range being captured by the camera by storing
the values differently than the stock picture profile.

 [12]: http://www.similaar.com/foto/flaat-picture-styles/long-1.html

I highly recommend shooting with one, if you're not going to make the
leap to shoot RAW. It does add the additional step in post-processing
of having to adjust the blacks/whites and/or applying a corrective
LUT (look up table) to adjust the end product to look less "washed
out". There are LUTs and plugins available for virtually every NLE
out there right now -- and I suggest learning how to do this. The
improvement in the end product is substantial for relatively little
time investment.

**Audio Post**

This is another section just for cinematographers.

The audio which is recorded with footage is generally "reference
audio", which is meant to be replaced by actual audio, generally
recorded with something like a [Tascam DR-40][13] or [Zoom H4n][14]
external recorder and a shotgun microphone. It's far outside the
scope of this to explain the majority of these technologies and
techniques, but sufficed to say that they produce far cleaner and
usable recordings than on-camera audio (even when using augmented
on-camera microphones, etc). If you can afford it, use external
audio, and have an experienced audio engineer perform some basic
post-production on your audio.

 [13]: http://tascam.com/product/dr-40/
 [14]: http://www.zoom.co.jp/english/products/h4n/

If you can't afford it, or don't have an audio engineer, there are
a few basic steps to get cleaner audio.

1) *Don't use the microphone built into the camera*. It sounds pretty
awful, and is noisy. Get a lav microphone for interviews, or a
directional hot-shoe mounted external microphone for anything else.

2) *Adjust the audio levels manually*. Automatic level adjustment is
going to be terrible. It's meant to avoid clipping, but it tends to
make the noise floor (the level of background noise) jump around as
the camera readjusts the audio recording level, so it may make your
life significantly more difficult when it comes time to adjust the
footage later. Adjust it to the loudest sound you're going to be
recording -- then perhaps a click lower, for safety.

3) *Respect the inverse square law*. For those unfamiliar, sounds
drop at a logarithmic rate as you move away from the sound source,
following the same inverse square law which is used to figure light
source brightness. The closer you are to a recorded sounds, the
cleaner and better the source audio will be. Every object which a
sound hits will produce a "reflection" (much as light does). If that
reflection is equal or louder than the volume of the source sound,
you're going to get a pretty terrible sounding audio recording.

4) *Get the cleanest audio possible*. Try to cut down on external
noise sources. Never assume that you can clean something later on;
you should be trying to get clean audio. If something has to be
re-taken to avoid a lawnmower being run in the background, then you
should seriously consider doing it. It'll save you from pulling out
your hair.

I'm sure that this isn't a *comprehensive* list, but hopefully this
will help everyone get started with deciding what, if anything, to
relegate to their post-processing workflow. Good luck!

