---
title: IMAP Synchronization
author: jeff
layout: post
permalink: /2010/01/17/imap-synchronization/
categories:
  - Development
  - Hacks
tags:
  - hack
  - imap
  - java
  - synchronization
  - tool
---
# 

I hate it. IMAP Synchronization, that is.

In an effort to migrate users from one \*shudder\* Exchange provider to another (after getting shot down for proposing first Zimbra, then standard mail server stuff, then [Openchange][1]), I have been going through all of the available IMAP sync software that I could find.

 [1]: http://www.openchange.org/

**mbsync** () – We use this for IMAP backup, so I figured it would be a good idea to try it for syncing between two IMAP servers. \*Crash\*. \*Segfault\*. This is one of the reasons I’m not a big fan of really low-level apps written in C.

**imapsync** () – Written using a Perl library, this offered the promise of fast syncing, and appeared to work in test runs. That is, until it encountered folders with spaces in them, and threw up all over the terminal. Really, it wasn’t a use-case for \*anyone\* to have spaces in folder names? I could have put some effort into fixing the library and/or script, but I figured that if something that basic wasn’t working for a fairly mature library, this wasn’t going to be pretty.

**The Imap Migration Tool** () – Written in PHP, with a two or three step process. Was meant for moving stuff, not keeping them in sync, so running multiple times would cause additional copies of messages to be created. Also, it seems to have been written in some prehistoric form of PHP, which required hacking to get it even marginally functional. Even then, it spat tons of warnings and nasties, which made me a little nervous to use it on any important mailboxes.

**mailsync** () – I don’t even remember why this one didn’t work, only that I wasted a fair amount of time playing with it to get it to try to migrate using the scheme we were working with to no avail. Scratch another one.

Solution … I had to roll my own. This is \*stupid\* to the highest degree, but I rolled something using [javamail][2] into a self-contained “fat jar” using [fatjar][3]. It works sickeningly well, and actually respects existing messages by message id, so that if for any reason I have to break the sync process, it’ll skip past anything it has already done. I made it non-destructive because it seemed like seriously bad juju to have a sync tool purge out email…. If I get permission from work, I’ll post the jar for anyone with Java 1.6 to use.

 [2]: http://java.sun.com/products/javamail/
 [3]: http://fjep.sourceforge.net/

As an aside, it took a little bit of hackery to get fatjar running outside eclipse. The relevant section of build.xml was:

    
      
    
      
      
      
      
      
    
      
        
          
          
          
        
      