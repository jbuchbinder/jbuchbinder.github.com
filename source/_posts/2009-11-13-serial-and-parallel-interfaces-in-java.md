---
title: Serial and Parallel Interfaces in Java
author: jeff
layout: post
permalink: /2009/11/13/serial-and-parallel-interfaces-in-java/
categories:
  - Development
---

To sum up before I even begin: they \*suck\*.

One of Java’s exceptionally weak points is serial and parallel interfaces, since it’s not within the normal bundled class library specification. In developing for Linux systems, I found that there are two basic routes you can take, being [Java Communications API][1] and [RXTX][2], with the latter being a reimplementation/extension of the former. To say that these are painful to work with doesn’t adequately state the gravity of the situation.

 [1]: http://java.sun.com/products/javacomm/
 [2]: http://users.frii.com/jarvi/rxtx/

For example, the *javax.comm.properties* file needed by both libraries has to exist in the classpath or buried deep in the JRE. This is an offshoot of the issue that they require JNI libraries to function, which debian handles nicely in the form of a librxtx-java package which does most of the heavy lifting with the exception of that nasty properties file. In dealing with a J2EE app, this becomes a pain if you want to stick with the “single file” WAR deployment. Eventually I baked an additional instruction into my build.xml file to relocate the properties file on execution.

The documentation for rxtx, at least in terms of practical examples, is horrid. The wiki server isn’t up and running (at least when I went to look) and the only evidence that anyone had ever tried to use this library for the purposes I was looking to use it for were a few old javadocs and a handful of mailing list entries.

This really should \*not\* be this painful. Virtually every system targeted by the JRE has I/O devices which should be covered by the scope of the basic class libraries. I should not have to practically reinvent the wheel simply to push data out to a peripheral.

By the look of the documentation, this wouldn’t have been any easier doing it with Windows, and I believe I managed to kill its ability to be cross-platform in any meaningful sense when I decided to use RXTX. This is just as bad as those asshats who make completely crossplatform applications then tie them intrinsically to Windows in some completely brain-dead way for no apparent reason.

Hey Sun, when you made this specification, could you have possibly thought to include support for devices which have been around since [1969][3] … 

 [3]: http://en.wikipedia.org/wiki/RS-232
