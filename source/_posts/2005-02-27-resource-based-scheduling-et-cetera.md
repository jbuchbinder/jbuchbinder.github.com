---
title: Resource Based Scheduling, et cetera
author: jeff
excerpt: Working on a resource-based scheduler for FreeMED
layout: post
permalink: /2005/02/27/resource-based-scheduling-et-cetera/
categories:
  - FreeMED
---
# 

This weekend I have been putting in some enormous amount of overtime, working on a rehaul of a few of FreeMED’s features. In particular, I have been pounding away at getting the scheduler completely rewritten, since the current one was only supposed to be a temporary hack. We’re moving to a template-driven resource-based scheduler, which so far seems to out-perform the old one in terms of usability and efficency. We’ll see if it progresses far enough for me to replace the old scheduler in CVS.

I’m also working to try to set up “ticklers”, which allow the system to perform actions at specified times (even when no one is logged in, et cetera) and “notifications”, which can be set to remind providers of impending events, since even the most fastidious would forget to follow up on something that occurred six months ago with no notification. 

In summary, development is steamrolling along. Everything is being documented as we’re going, so hopefully other people won’t be so bashful about contributing code …