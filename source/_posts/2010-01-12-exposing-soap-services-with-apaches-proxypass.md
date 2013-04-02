---
title: 'Exposing SOAP Services with Apache&#8217;s ProxyPass'
author: jeff
layout: post
permalink: /2010/01/12/exposing-soap-services-with-apaches-proxypass/
categories:
  - Development
---
# 

I have recently had cause to proxy a J2EE CXF service through an apache 2.2 instance, and thought it would be nice to share my findings. (This was all done on a Debian system.)

First of all, the mod_proxy pieces have to be enabled using **a2enmod proxy**.

A fragment has to be added with the proxying bits and some limitation:

    
         Order allow,deny
         Allow from all
    
    
    ProxyPass /EXPOSEDURL http://SERVER:PORT/URL
    ProxyPassReverse /EXPOSEDURL http://SERVER:PORT/URL
    

Reloading apache configuration should enable the proxy properly. The only other possible issue is that in addition to the WSDL URL, you’re going to have to specify a “proxy” URL, which is just the service URL without ?wsdl at the end of it. A fragment of PHP’s SoapClient would look like this:

    $url = "http://server.domain:8180/services/MySoapService?wsdl";
    $sc = new SoapClient( file_get_contents($url), array(
              'login' => $my_username // optional for basic auth
            , 'password' => $my_password // optional for basic auth
            , 'compression' => SOAP_COMPRESSION_ACCEPT | SOAP_COMPRESSION_GZIP
            , 'location' => str_replace('?wsdl', '', $url) // force this to work through proxies
    ));
    

The magic in that last segment was the “location” parameter, as it specifies the proxy. Good luck!