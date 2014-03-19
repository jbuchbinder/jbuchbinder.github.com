---
title: Backing up MAPI contacts and calendar from Exchange Server
author: jeff
layout: post
permalink: /2010/01/22/backing-up-mapi-contacts-and-calendar-from-exchange-server/
categories:
  - Hacks
---

I have a hate/hate relationship with Exchange Server. I hate it, and I’m pretty sure it hates me.

Why someone would design a system to expose every bit of data for a system through a nice standard protocol like IMAP, then only allow certain things to be viewed through a piece of crap proprietary protocol like MAPI just boggles the mind. I’m sure it’s part of their “vendor lock-in” thing, but it just pisses me off.

Anyway, I found out that to completely backup an Exchange account (as I have been doing over the last week or so for different accounts), you also have to backup the non-mail portions. I ended up using a deprecated library called [Jakarta Slide][1] for WebDAV client support, which helpfully came with a **SearchMethod** call which was capable of running the specialized XML query required to backup the data.

 [1]: http://jakarta.apache.org/slide/clientjavadoc/overview-summary.html

The XML I ended up using was:

    
    
    
    SELECT * FROM "URL"
    
    
    

in case anyone is interested. Again, I have a fatjar of this utility, but I have to check with work to make sure they’re okay with me releasing it before I can post it anywhere.
