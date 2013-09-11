---
title: No more hotlinking images
author: jeff
layout: post
permalink: /2006/09/27/no-more-hotlinking-images/
categories:
  - Hacks
---

For those who use [Apache 2.x][1], this is a nice trick to keep people from hotlinking your images. I’ve seen a few variants of it, but this one I picked up most recently from a [slashdot comment][2], of all places.

 [1]: http://httpd.apache.org/
 [2]: http://slashdot.org/comments.pl?sid=197769&cid=16205407

Make sure you have enabled mod_rewrite, then add this in your `.htaccess` file for any directory with images in it:

```
 RewriteEngine on
 RewriteCond %{HTTP_REFERER} !^http://(www.)?yourdomain.com [NC]
 RewriteRule .* /files/goatse.jpg [NC,L]
```
to redirect to an awful image, or use my own personal variant:  
```
 RewriteEngine on
 RewriteCond %{HTTP_REFERER} !^$
 RewriteCond %{HTTP_REFERER} !^http://(www.)?sitename.com/.*$ [NC]
 RewriteRule .(gif|jpg|png)$ - [F]
```
which doesn’t return *anything* if someone else hotlinks your images. If they like your images enough, they can like them enough to save a copy on their own webserver.

