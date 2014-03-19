---
title: JasperWrapper
author: jeff
layout: post
permalink: /2010/01/31/jasperwrapper/
categories:
  - Development
---

I have just wrapped up (no pun intended) work on an initial version of a CLI [JasperReports][1] wrapper, based heavily off the work of [jasperCall][2]. It’s also quite similar to the work being done on [RunJasperReports][3], although it was specifically designed to be integrated into [FreeMED’s][4] reporting engine, as it is put together as a fatjar. It currently supports PDF, XML, XLS and HTML output, and should theoretically support parameter passing, though I haven’t tried it out yet. It has a newer version of [MySQL Connector/J][5] baked in as well, so it shouldn’t require any external libraries outside a standard JRE install to function properly.

 [1]: http://jasperforge.org/projects/jasperreports
 [2]: http://jasperforge.org/plugins/project/project_home.php?group_id=97
 [3]: http://code.google.com/p/runjasperreports/
 [4]: http://freemedsoftware.org/
 [5]: http://www.mysql.com/products/connector/

The code can be check out of anonymous Subversion from  if anyone is interested in building it. (It obviously should require Java 6 JDK to compile properly.) Hopefully I’ll get around to tagging and releasing versions of it for download shortly, if anyone shows interest in it.
