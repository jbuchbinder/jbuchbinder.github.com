---
layout: post
title: "Checking for deprecated Wordpress functions"
date: 2013-11-13 15:29
comments: true
description: A script to help make Wordpress development a little less painful.
cover: 
categories: 
 - Development
 - Hacks
---

One of the major pains involved in Wordpress development and work (and one
of the reasons why this isn't hosted on Wordpress anymore) is that of their
quickly changing API.

I've encountered issues where plugins have suddenly (and quietly) stopped
functioning, due to a deprecated function call being removed from the
Wordpress API. I'm sharing my "solution" to this issue, which is a script
(which can be integrated into a CI system), which scans your plugin and/or
theme code and gives you a list of the deprecated functions you're using,
as well as where they exist in your code.

{% gist jbuchbinder/7419000 %}

