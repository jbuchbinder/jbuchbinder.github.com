---
title: 'Xela Day Five: FreeMED, Finally'
author: jeff
layout: post
permalink: /2010/09/23/xela-day-five-freemed-finally/
wpbook_fb_publish:
  - yes
  - yes
categories:
  - FreeMED
  - Remember, No One Cares
---
# 

It’s day five of our trip to Xela, and we’ve come to the realization that the damn server isn’t going to clear Customs before I leave the country. That being understood, I got FreeMED up and running on the machine which was originally designated to be the secondary / failover server. The guy who set up the router which is being used by POP-WUJ is unfortunately in Spain, and has left no information on access, so I’m unable to appropriately set up port forwards for the server. In lieu of that, autossh tunnels are now running back to Connecticut, so I can still access the server. It’s just not very conducive to anyone \*else\* trying to access the server from beyond the walls of the POP-WUJ building.

All of this was done despite efforts from my day job to occupy as much of my vacation as possible with fixing firewalls and failing over between colocation centers. That ate up the middle of my day, for the most part. While I was busy doing this, Jonathan and the part of the crew that hadn’t gone out hiking at 4am started work on beautifying and improving the clinic. By 5 or 6pm (as everyone else got back around 2pm), the pediatric exam room had been repainted and decorated, the main room had been decorated, and much had been improved in the pharmacy and in the electrical system areas. Thanks to my sister Shelley, there are nice printed signs which are to hang on the exam room and pharmacy doors, and a large tapestry hangs where a few photos had been haphazardly taped to the walls. Jorge painted the walls in the pediatric exam room with a roller, adorned with a plastic ziplock bag over his head and a surgical mask, and some of the nurses attached a semi-permanent measuring tape to the wall for height measurements, decorated with cutouts of popular childrens’ characters. With any luck, the kids who are seen in the clinic will feel much more at ease when they visit the doctor.

All of us went out for Tex-Mex food at a local eatery with Meg and her husband. I broke from my tradition of only eating local food to help myself to a grilled burrito “de res con queso” with beans and flavored rice, with a helping of the local beer. It was offered in light, dark, and “medium”, which we surmised was made by mixing equal parts of the light and dark brews. Regardless, it was a good tasting meal. I grabbed a chocolate flavored coffee, and Irv grabbed a regular, to help keep me up for a stint of finishing up the triage UI logic. I ended up going with a system event bus approach, in that new registrations are pushed out via “systemnotifications”, forcing the UI to update itself whenever new patients are registered at the registration stage. This should allow the triage person to see all registrations as they come in from a single screen which does not require any sort of manual refreshing to function properly.

The crew is splitting in half tomorrow. One half is visiting a daycare in the pueblos outside of town, and the remainder, including Irv and myself, are staying behind with Dr Christian to man the clinic in Xela. I’m staying behind so that I can help push adoption of the EMR for demographics and vitals collection, and Irv will be assisting Dr Christian in seeing as many patients as they can. The hope is that we can break for a while to visit the marketplace, as I promised my wife I’d buy her some local fiber, yarn and other knitting supplies. If I’m lucky, I can find a local artisan who makes instruments — but I’m not holding my breath.