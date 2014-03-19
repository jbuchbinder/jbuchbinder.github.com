---
title: Pluggable Authentication for FreeMED
author: jeff
layout: post
permalink: /2005/10/19/pluggable-authentication-for-freemed/
categories:
  - Development
  - FreeMED
---

I finally mustered up the spare time to move from the old system of [FreeMED][1] authentication to a pluggable system. I have only coded up two plugins for now: a “Password” plugin, which uses the old system of authentication and password checking, and a “Basic” plugin, supporting HTTP Basic Authentication. I’m also currently considering writing an LDAP plugin to allow FreeMED credentials and basic ACL information to be stored on an LDAP server, to really allow for enterprise deployments. On top of all this, I have been doing some “house cleaning” in the code so that FreeMED is more autonomous on startup.

 [1]: http://freemedsoftware.org/
