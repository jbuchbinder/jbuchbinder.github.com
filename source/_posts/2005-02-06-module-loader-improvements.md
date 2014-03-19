---
title: Module loader improvements
author: jeff
excerpt: New features in FreeMED module loading
layout: post
permalink: /2005/02/06/module-loader-improvements/
categories:
  - FreeMED
---

I just added the ability to span directories in FreeMED’s module discovery routines. (Actually, they’re implemented in phpwebtools, but the idea is the same … ) This makes it much easier to seperately version portions of FreeMED, either for branding purposes or just for non-official modules, by allowing entire directories to be seperately versioned.

This probably doesn’t make anyone nearly as happy as it makes me, but it’s a step in the right direction for doing things the Right WayTM.

Well, that and the fact that I have been putting this change off for months and finally got around to doing it … For anyone interested, it’s currently in the CVS versions of [FreeMED][1] (0.8.0) and [phpwebtools][2] (0.4.5).

 [1]: http://sourceforge.net/projects/freemed/
 [2]: http://sourceforge.net/projects/phpwebtools/
