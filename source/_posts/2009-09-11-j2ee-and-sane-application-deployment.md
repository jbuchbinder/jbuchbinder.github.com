---
title: 'J2EE and &#8220;sane&#8221; application deployment'
author: jeff
layout: post
permalink: /2009/09/11/j2ee-and-sane-application-deployment/
categories:
  - Development
---

As I have been delving deeper into the J2EE Servlet specification during the rewrite of [REMITT][1], I have been learning some very interesting, and sometimes very painful, lessons about trying to package something without requiring complicated installations.

 [1]: http://remitt.org/

To get authentication working in Tomcat, the normal way is to define a Context and Realm in TOMCAT_HOME/conf/server.xml. A relatively undocumented file called META-INF/context.xml allows fragments to be distributed with war files. This would be a great solution if it didn’t mean that authentication was now deeply dependent on editing a file in the web archive, which kind of takes the advantage completely out of having one. D’oh!

Next up was the idea of using JAAS, which is a way of setting all of the security information in a single configuration file, and using a custom security module. Which would work very well, if I wanted to pre-extract the war file and pass an archaic system property file through JAVA_OPTS. This seems, again, too difficult to make any sort of sense.

I eventually found a solution by creating my own [Filter][2] and [LoginModule][3], then setting the system property for the [JAAS configuration][4] manually in the init() portion of the Filter. A little filter and realm information in [WEB-INF/web.xml][5], and everything seems to work somehow. I understand that the Servlet guys wanted to make sure that the J2EE server context and app context were at two different levels (hence the reason a DataSource in META-INF/context.xml or tomcat’s conf/server.xml isn’t writeable at all), but it makes it a mess for clean deployment.

 [2]: http://svn.freemedsoftware.org/remitt/trunk/src/org/remitt/server/jaas/SecurityFilter.java
 [3]: http://svn.freemedsoftware.org/remitt/trunk/src/org/remitt/server/jaas/HttpLoginModule.java
 [4]: http://svn.freemedsoftware.org/remitt/trunk/war/WEB-INF/login.conf
 [5]: http://svn.freemedsoftware.org/remitt/trunk/war/WEB-INF/web.xml

As it stands now, I can run the server with an override file like like:  
`JAVA_OPTS="-Dproperties=/my/remitt.properties" ./bin/catalina.sh start`

And I think that’s worth the hassle to set up, since it makes deployment a breeze.
