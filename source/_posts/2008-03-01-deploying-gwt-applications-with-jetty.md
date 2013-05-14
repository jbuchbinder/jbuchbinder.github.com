---
title: Deploying GWT Applications with Jetty
author: jeff
layout: post
permalink: /2008/03/01/deploying-gwt-applications-with-jetty/
categories:
  - Development
  - Hacks
---
# 

I’m not a big fan of tomcat, preferring [Jetty][1] where possible. Unfortunately there are a lot of catches involved with getting [GWT][2] applications working. I’ll try to break the changes down here. This assumes that you already have a GWT project built and made with projectCreator which you are migrating into Jetty.

 [1]: http://www.mortbay.org/
 [2]: http://code.google.com/webtoolkit/



1) Pull the start.jar, bin/jetty.sh script (which will be moved to the base of your distribution), lib and etc directories from your Jetty distribution, and put them in $DIST (your distribution directory)

2) Change your (appname)-shell script to be like the following:  
**JettyTest-shell**  
``
#!/bin/sh
GWT_HOME=/usr/lib/gwt
ENTRY_POINT=net.cognitiveconsulting.gwt.JettyTest
HOST_PAGE=JettyTest.html
APPDIR=`dirname $0`;
CPGWT=$APPDIR/src
CPGWT=$CPGWT:$GWT_HOME/gwt-user.jar
CPGWT=$CPGWT:$GWT_HOME/gwt-dev-linux.jar
java -cp $CPGWT com.google.gwt.dev.GWTShell -logLevel DEBUG -noserver -port 8080 "$@" $ENTRY_POINT/$HOST_PAGE
``

3) Change your (appname)-compile script to look like:  
**JettyTest-compile**  
``
#!/bin/sh
APPDIR=`dirname $0`;
echo "Compiling GWT portion of application ... "
java  -cp "$APPDIR/src:$APPDIR/bin:/usr/lib/gwt/gwt-user.jar:/usr/lib/gwt/gwt-dev-linux.jar" com.google.gwt.dev.GWTCompiler -out "$APPDIR/webapps" "$@" net.cognitiveconsulting.gwt.JettyTest;
echo "Compiling native Java part of application ... "
ant -f net.cognitiveconsulting.gwt.JettyTest.ant.xml
echo "Moving pieces into Jetty library path ... "
( cd bin ; jar cf ../lib/net.cognitiveconsulting.gwt.JettyTest.jar * )
``

Remember, after this, your output directory is no longer www, it’s now “webapps”.

4) Create the directory $DIST/webapps/(appname)/WEB-INF, and create a web.xml file like this, with the definitions for your remote services:  
**webapps/net.cognitiveconsulting.gwt.JettyTest/WEB-INF/web.xml**

    [servlet]
        [servlet-name]Test[/servlet-name]
        [servlet-class]net.cognitiveconsulting.gwt.server.TestImpl[/servlet-class]
      [/servlet]
    
      [servlet-mapping]
        [servlet-name]Test[/servlet-name]
        [url-pattern]/rpc/net.cognitiveconsulting.gwt.client.Test[/url-pattern]
      [/servlet-mapping]
     
    

(Please note that because wordpress ate my XML, I used a different kind of brackets, please substitute as required.)

5) Create the ant build file:  
`/usr/lib/gwt/projectCreator -ant net.cognitiveconsulting.gwt.JettyTest`

6) Make sure you have created working servlets under the internal tomcat implementation before you proceed, making sure that the servlet information is in the .gwt.xml file in your source directory like this:  
``

7) Make sure that a copy of $GWTDIR/gwt-servlet.jar and any other libraries you are using are installed in $DIST/lib — forget this and nothing is going to work.

8) Create an empty “logs” directory under $DIST.

You should be able to start Jetty at your convenience and browse to the (appname)/(startpage).html page. If you want to pack it as a war, just zip the (appname) directory in $DIST/webapps with a .war extension. Also, running jetty.sh with the parameter “supervise” will allow you to watch the logs as they go by.

Hope this has been informative and helpful.

**UPDATE**: *Jan, one of the webtide guys, was nice enough to send me an ant build file which does much the same type of thing I was attempting to do here. It is attached [here][3], for anyone else who would like a copy.*

 [3]: http://jbuchbinder.com/wp-content/uploads/2008/03/build.xml
