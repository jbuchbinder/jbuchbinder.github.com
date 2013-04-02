---
title: 'Xela Day Four: Aldea Pujujil'
author: jeff
layout: post
permalink: /2010/09/23/xela-day-four-aldea-pujujil/
wpbook_fb_publish:
  - yes
  - yes
categories:
  - FreeMED
  - Remember, No One Cares
---
# 

Today we left early in the morning, around 7am, to head out to the village of “Aldea Pujujil” in Solola, Guatemala to do a travelling clinic. We took two “micro buses” with ten to thirteen people in each with equipment tied down to the top, and left Xela heading back towards Guatemala City on the Pan American Highway.

The local town had set up their central meeting building, which was a stone edifice with a grooved tin roof, as a sort of makeshift clinic. There were individual treatment “rooms” created by hanging wire with plastic garbage bags and painter’s tarps, and a large tarp separating the main registration and triage area from the rest of the “rooms”. Five separate treatment areas were available, in addition to an area for the dentist who came with us. More than half of the prospective patients spoke qui’che instead of spanish, so there were a few local translators to help the doctors, registration and triage crew.

The children there seemed very shy at first, but were enamored by the doctors, having their pictures taken, and having balloons made for them by the nurses and me out of spare latex gloves. In the afternoon, the local school emptied out at the same time as the daily rain, so the “clinic” area was flooded with refugees from the water. They quickly joined in playing with the inflated gloves and posing for pictures with the clinic crew. It was interesting to see that two of the boys were using old Corn Flakes boxes as protection from the rain.

Even though I had the job of documenting the clinic visit with photos for POP-WUJ fundraising to get more supplies to do this sort of thing in the future, I couldn’t help but feel a little helpless. The people who came needed medical help, some more than others, and the most I could do was try to make the children laugh a little and stand out of the way as a silent observer of the doctors trying to help this village, which, if lucky, would see these doctors a few times a year. Unfortunately, as the paper process used to see patients is pretty inefficient at best, we probably could have helped more people if we had a way to organize this better. The “distance workstation” project I’m looking at starting should help out with that, if I can clear some minor technical hurdles in the implementation department.

After a few hours in the bus, we came back to the clinic. Irv, Shelley and I stayed at the clinic and kept the door open so I could work a bit more there, and we headed back to the hotel around 7 or 8pm local time. Irv, Jorge and I went to a little restaurant called “Cafe Shalom” (alternately spelled “Cafe Shalon” on half of the posters) near Parque Central, and had a brief dinner, then walked back.

Back to the medical record… The server is stuck in customs in Guatemala City somewhere, so I had to get the secondary server up and running. It had been slightly damaged in transit, which jostled the RAID card loose and knocked a few connectors off of the backplane. Regardless, after my father made a quick trip to the local bookstore to pick up a blank CDR (as the BIOS in that model didn’t properly boot off of my Debian USB install key due to its particular vintage), I got Debian running on that machine with little trouble. The uplink here isn’t fantastic, so it’s a matter of starting the upgrades and downloads then walking away for a while. There are also some electrical system issues. The single outlet available to us is ungrounded, which may cause some issues, so we’re arranging a UPS to be purchased locally to act as a bit of a safeguard between the fairly unstable electrical grid in Xela and the servers and switching hub. We may have to drill a post to ground the system to the earth properly in addition to all of that.

I’m making pretty good headway with FreeMED modifications for the clinic, and have started on the triage screen, with some input from Jorge. I’m hoping that it can act as a “junction” in the flow of data around the clinic, but that remains to be seen. After I finish up the screen tomorrow, I’ll do some limited implementation testing to see how well it works or doesn’t work.