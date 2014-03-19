---
title: Project Review 2011
author: jeff
layout: post
permalink: /2011/12/28/project-review-2011/
wpbook_fb_publish:
  - yes
  - yes
categories:
  - Development
  - FreeMED
---

I’ve been a bit lax in posting about my work here, mainly because Twitter makes you lazy. (Why write complete sentences when you can summarize in 140 characters or less?)

Here are some of the projects I’ve been working on over 2011, with some links. I’m sure I have left some out.

*   [FreeMED][1] – opensource electronic medical record/practice management system. Did a fair amount of retooling, including i18n, for the installation in Xela.
*   [ganglia][2] – opensource metrics aggregation system. [Vlad][3] and I managed to get a 3.2.0 release out the door, and are working on 3.3.0
*   [ganglia web 2.x][4] – updated web interface for ganglia
*   [haproxy][5] – API work, to allow programmatic manipulation and querying
*   [nagios][6]/[icinga][7] – API patches to allow programmatic manipulation of Nagios/Icinga
*   [nagios-dash][8] – a jquery-based Nagios replacement dashboard for NOCs. Requires the aforementioned nagios/icinga API patch.
*   [node-soap][9] – SOAP bindings for node.js. My work mostly involved fixing and expanding authentication methods.
*   [REMITT][10] – my medical billing engine. Modernized for 5010 transactions.
*   [statsd-c][11] – C port of etsy’s “statsd” server. Written in C primarily for speed.
*   [sugarsync-linux][12] – sugarsync linux API client. As Sugarsync isn’t too hot on providing a native Linux client, I took it upon myself to write one in Vala.
*   [vded][13] – “vector delta engine daemon”. Meant to allow metric collection for ever increasing values over time. (My first foray into “Vala”)

 [1]: http://freemedsoftware.org
 [2]: https://github.com/ganglia/monitor-core
 [3]: http://vuksan.com
 [4]: https://github.com/jbuchbinder/ganglia-misc
 [5]: https://github.com/jbuchbinder/haproxy
 [6]: https://github.com/jbuchbinder/nagios/tree/nagios-3.x-api
 [7]: https://github.com/jbuchbinder/icinga-core
 [8]: https://github.com/jbuchbinder/nagios-dash
 [9]: https://github.com/jbuchbinder/node-soap
 [10]: https://github.com/freemed/remitt
 [11]: https://github.com/jbuchbinder/statsd-c
 [12]: https://github.com/jbuchbinder/sugarsync-linux
 [13]: https://github.com/jbuchbinder/vded
