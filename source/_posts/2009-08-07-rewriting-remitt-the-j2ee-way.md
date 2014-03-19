---
title: Rewriting REMITT, the J2EE Way
author: jeff
layout: post
permalink: /2009/08/07/rewriting-remitt-the-j2ee-way/
categories:
  - Development
---

For those people who are unfamiliar with my programming ventures, I had written a three stage extensible billing system a few years back called [REMITT][1] (which stands for REMITT Electronic Medical Information Translation and Transmission). I had created the majority of the code in about a week and the XSL transforms required for it to function in another two weeks or so.

 [1]: http://remitt.org/

Since then, the project has been somewhat languishing, due to it being written in Perl, which is a minor pain to get running for most people on a good day, compounded with it using XML-RPC with sessions as a remote procedural call dialect.

I decided to embark on a complete rewrite of the core of REMITT to make it more portable, more extensible, better designed and far more stable than it had been in past. I have gotten about 3/4 of the way through rewriting the core of REMITT as a J2EE application using MySQL as a database backend. There are a number of improvements I have been working on, including:

1.  True crossplatform nature. – Being J2EE, you can even run it on \*shudder\* Windows if you felt the need to. I wouldn’t recommend it, but you could do it.
2.  Better threading model. – Instead of a single executor thread pool, each stage of transformation gets its own pool, maintained and reaped by a single control thread. As Java has a very nice threading model, this was much easier than I had anticipated.
3.  Transport scripting. – Instead of requiring heavy-duty programming expertise to write transport plugins, I moved to using Rhino do do embedded Javascript scripting for them, as well as allowing SFTP transport.
4.  Namespaced configuration. – Each user can have their own configuration \*per\* plugin, which is a lot easier than before. It also has the ability for each plugin to present its configuration options to a frontend, so there’s no more worrying about configuration variable names.
5.  SOAP. – I’m using CXF for web services, and it took me all of a second to generate a proxy class using wsdl2php which worked perfectly the first time around.
6.  Web Interface. – Through the magic of JSP, the REMITT server has its own set of administration pages and monitoring functions, so it’s not quite as much of a black box as before.
7.  IDE Support. – Eclipse is a beautiful IDE, and with Javadoc completion support, makes anything I could have used with Perl look like crap. ‘Nuff said.
8.  OO Model. – Perl OO is to Java OO as a Pinto is to a Tesla Roadster. This thing actually has some architecture behind it. It’s about time.

I’ll be posting the code into REMITT’s SVN trunk shortly, as soon as I’m positive that it does \*something\* in case anyone else feels the need to work on it. In the meantime, I’ll continue to play with it until I get something useful out of it.
