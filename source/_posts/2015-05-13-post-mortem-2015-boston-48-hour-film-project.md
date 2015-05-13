---
layout: post
title: "Post-Mortem: 2015 Boston 48 Hour Film Project"
date: 2015-05-13 13:12:42 -0400
comments: true
description: Analyzing and documenting our entry in the 2015 Boston 48 Hour Film Project
cover: /images/2015/05/2015_boston_48.jpg
cover_width: 815
cover_height: 315
categories: 
 - Film
 - Post-Mortem
---

For the second time, my 48 Hour Film Project team, [Shoot the Moon Films](http://shootthemoonfilms.com), decided to enter the Boston 48 Hour Film  Project for the 2015 event -- along with 89 other teams. What follows is my record of both the timetable/process we used and a post-mortem analysis of the flaws and potential improvements in our processes in creating "Acceptance".

<!-- more -->

## Day One: Preproduction, Kickoff, Writing, and Planning

The production designer/co-writer and I made a trip out to the location which we had confirmed, and took pictures and notes so that the writers would have some idea of the spaces which we needed to work in, picked up some cases of caffeinated beverages for the next day, and we headed back to the house for an hour before kickoff.

Our producer, Curtis, went into Boston for the kickoff event so that we didn't have to worry about drive time to and from cutting into writing time, and we got our constraints at 7:00pm on Friday. Both of our writers were set up with collaborative script-writing software, and by 10:30 - 11:00pm we had a final draft of the script, and had dropped copies to the actors and crew by 11:15pm. I made a bundle of copies on the laser printer so we'd have on-set copies for all those actors who didn't have printers, since it's frustrating to have actors reading off of their phones.

I stayed up until about 3:00am deconstructing the script and making shot prep notations, diagrams, and shot lists for the 1st AD. Everything was left on the chargers, and all non-battery-powered cases and boxes were loaded into the car.

## Day Two: Filming

My wife and I woke up around 6:00am to both load the car with equipment and finish constructing a dead-cat style wind cover for the blimp that one of our friends had designed and constructed for the boom mic to facilitate shooting outside. After taking care of general household tasks and loading the car, we headed over to meet the other department heads and the early arrival actors about twenty minutes from our place.

The first order of the day, after hair and makeup had been set up, was to create some collateral items for the set design. We took our actors to a secondary location, posed them, and took a series of photos -- and after picking the best of those, we sent a crew member to a nearby store to get a frame and print a copy. Voilà! One framed picture, created in less than an hour.

One of our actors had to undergo a fairly radical makeup/hair transformation, which ended up taking longer (about four hours) to perform in total than it took our writers to produce the script. Thankfully we were able to stage out the first scene and get equipment set up for the first shots, as well as blocking, while he was in hair and makeup.

The outdoor shots were made easier by the new boom rig, but more difficult by the periodically changing light levels from clouds blocking the sun. I slightly tweaked the vari ND filter we were using to try to keep the light level perceptually the same, but any remaining variances would have to be fixed in post.

As soon as the first scene was done, we blocked out the next set of scenes and broke for lunch, as it was after noon. Our craft services guy, David Emigh, was custom-cooking pizzas in his portable outdoor brick oven -- among other delicious foodstuffs. Our AD kept everything moving along by keeping the break down to 30-40 minutes so we could keep going.

As our last scene involved shooting around magic hour, we had to finish the rest of principal photography before then. We finished with about an hour to spare -- mostly by keeping the complexity of most of the shots down other than a handful of intricate shots which had been pre-planned as such.

We finished up the last scene worth of shooting outdoors for magic hour, and with the help of our talented lighting designer, we set up a pretty fantastic ending shot for the film. Principal photography: wrapped.

Everyone headed back to my place to celebrate principal photography being wrapped and eat dinner while I offloaded the footage onto one of the on-board 2TB hard drives in the editing machine. (Due to a combination of the motherboard's chipset and Windows 7, anything larger than 2TB tends to be corrupted after a few uses -- serves me right for using Windows for *anything* important, right?) It took about 40-50 minutes in total to offload over the eSATA dock interface the ~420GB of footage we had taken, plus a few gigabytes of sound files from the H4n.

For our last project, I had used Media Encoder to batch encode 1080p H.264 proxies from the 4K ProRes HQ footage so that the machine would require less horsepower to edit the footage. This time around, I ended up using the Blackmagic Design 4K 23.97fps native sequence profile in Premiere; this allowed direct editing of the footage without the extra time burns of creating proxies and offlining/replacing the footage.

The crew took turns sitting with me to help give perspective on the different scenes and shots (as well as keeping me awake during the editing process). We finished a rough cut around 11:00-11:30pm which weighed in at about 7 min 30 sec -- 30 seconds too long for the competition. We took the next hour or two and cut it down to 6 min 59 sec. Afterwards, I replaced all of the remaining on-camera audio with boom and room tone, and exported three basic exports: a 480p draft copy timecoded for our composer to score against, an OMF encapsulated export, and an OMF export with separate audio files. (The last two were redundant, but I always seem to send the wrong one, so I erred on the side of caution.) All files were uploaded to Google Drive and links shared with the audio post engineer and composer in Boston. 3:30am, and time to get a few hours of sleep. Nick (actor and production designer) was passed out on the beanbag chair -- on top of my corgi -- after having sat through the last stretch of the editing. I set my alarm for 6:00am, and grabbed a few hours of sleep.

## Day Three: Post-Production and Dropoff

Got up from the alarm to find a message from the composer checking in about confirming the theme / mood of the scoring. I answered that, and trotted down the road to grab myself a coffee so that I could get my eyes properly open.

I snagged Nick to help with the order of the credits (since I never get them right on the first try), and after verifying that the corgi made it through the night we cranked out the final credits, opening bits, and cards.

Nick and Jon (Demers) checked in on me periodically as I colored the remaining pieces of the film. After that, we rendered it out at full resolution and imported the video back into Premiere, then re-composited all of the titles, etc, from the original edit.

I paced back and forth to stay awake until the messenger notifications from Garett (scoring) and Aaron (sound design / post production) letting us know that they had a finished track. We pulled it off of Google Drive, then pulled a second version a few minutes later which Aaron had compressed a bit.

We rendered the final copy out at 1080p, since the 48 Hour Project didn't accept 2.5K or 4K output, and transfered the resulting output copy to my Linux workstation, where I created both a video DVD and a data disc with the original output as ISO images.

{% gist jbuchbinder/8c92bab118aa3ad02d8e %}

From there, we transfered the files to Curtis in Watertown, where he burned two copies of each format, tested them, and dropped them off (with a massive load of paperwork) to the dropoff point. Done!

## Post-Mortem Analysis

Overall, I was very happy with my team's performance. We managed to stay ahead of schedule most of the time -- and I believe that (as well as our output) came down to a number of important points:

 * **Time management**. Our ADs were always pushing us to keep moving, even in the face of delicious food and potential hardships. (That's a specific shout out to *Natasha Darius* and *Hannah Viens*. Natasha is my lovely wife -- but that doesn't stop her from being a force to be reckoned with when she's on set with us.)
 * **Prep time**. An hour of shot prep time is worth four hours of wasted on-set time, I've come to believe. The majority of the shots we used were pre-planned the night before, with sheets of diagrammed and enumerated shots for the 1st AD to make sure we didn't miss any necesary footage to complete our edit.
 * **Location scouting**. Being able to visit the location the night before made *worlds* of difference. Instead of having to adjust shots once we got there, I had a mental image of the layout; this made it much easier to create shot setups which would work with our real-world constraints.
 * **Crew**. Having the right crew members on-set made all the difference -- I absolutely *cannot* stress this enough. Having a 1st AC / focus puller who nails focus pulling on gimbal tracking shots consistently every time (Brandi Demers) keeps us from wasting time re-taking moving shots. Having a boom operator who can get consistently pristine audio every time (Paul Magrey) kept us from having to waste precious time in post-production trying to ADR or clean up unusable audio. Having a lighting designer / gaffer constantly fiddling with lights and adjusting everything to compensate for the movement of the sun (Debra Leigh Siegel) saved immeasurable time in post-production -- not to mention saving me time having to deal with lighting directly.
 * **Actors**. You can't create a convincing film without convincing actors. Everyone knew their lines and more importantly *knew their characters*.
 * **Good writing**. You can't put something together without good design and good planning, and the same is true for film. No matter how good your camerawork, how talented your actors, you will turn out utter offal if you don't have a good script underneath it all. Natasha and Nick turned out a fantastic engrossing script *ahead of time*, and I can't possibly praise them enough for it.
 * **Electronic transmission of deliverables**. Curtis Reid -- producer extraordinaire -- lives much closer to the delivery point for the Boston 48 than I do, so we made the decision to pre-render ISO images of the deliverable discs and push them up to him using Google Drive. He burned two copies of each format, tested them, then drove them in. This little piece of maneuvering saved us at least an hour of drive time.
 * **Batteries, cables, manifests**. We charged all of our rechargeable batteries for cameras, EVFs, sound units, et al the night before. We also made sure that we had backup cables (where possible) and every piece of equipment we were going to need for every planned shot was accounted for. (Our production designer also has a full kit with every possible essential in it, so we were also pretty well covered there.)
 * **Sound**. We put a lot of effort into getting the best sound possible, and it paid off. Having a moving score, courtesy of Garett Schmidt (with whom we had worked on [The Carving](/2014/10/19/another-48-hours/)) and sound design and post processing courtesy of his partner-in-crime Aaron Theodore Berton (who also worked with us on *The Carving*). Without them, the film wouldn't pack nearly the same emotional impact and would be much less enjoyable to watch.
 
As this is a post-mortem analysis, I'm going to also highlight some of the places where we could have improved a bit.
 
 * **Length**. We ended up having to cut the film down in places to make it come in under the seven minute mark (6m59s was the final length). It could conceivably be better to start with a shorter / tighter target, since we have a time limit range of 4 - 7 minutes to work with.
 * **Color matching**. I ended up eyeballing the color of my monitor, but having a color-match card does me no good if I can't make sure that my monitor is showing me accurate colors. I probably need to get one of these as soon as possible.
 * **Extensive hair and makeup delays**. As it took us almost four hours to get Nick in hair and makeup for this, we probably should have considered rolling first call back to earlier in the morning. If there's an insanely complicated job that has to be done which *everyone else* is waiting on, it makes sense to try to start it earlier. (It wasn't particularly possible for this project because we needed a piece of collateral with Nick *without* hair and makeup done.)
 * **Know your audience**. I don't know if this is a potential improvement or not, as we went into this competition trying to make the best 4 - 7 minute long film we could with the constraints we were given; it wasn't about trying to make something that would particularly *wow* judges. We only used a single gimbal shot, didn't have overt or crass gags, didn't oversaturate our footage, and broached two fairly controvertial topics. It's not a stretch to say that there's a pretty good chance that we might have done better in the context of the competitive awards if we had tried to play to what the judges wanted to see. That being said, I'm happy with the film, and wouldn't have changed it.
 * **Scrims**. The day was much brighter than forecasted, so we didn't bring any scrims or setups which could be parlayed into a decent scrim setup. This left the opening scene a bit "shadowed" in the actors' faces. It worked out because of the context of the scene, but it left everything feeling a little less cinematic than it could have been.
 * **Sound cards**. One place we fell down in the "preparedness" department was due to a lack of SD cards with enough available space for the boom rig when our primary card failed. Luckily, Curtis produced a 32 GB card (as if out of thin air) and we were able to continue on. Lesson: always have redundant storage cards -- flash media does tend to fail every once in a while.

I had a great time this year, and I'd like to thank my crew, cast, and post-production team for helping to turn out a fantastic film!
