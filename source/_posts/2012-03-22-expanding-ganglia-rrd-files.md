---
title: Expanding Ganglia RRD files
author: jeff
layout: post
permalink: /2012/03/22/expanding-ganglia-rrd-files/
wpbook_fb_publish:
  - yes
wpbook_message:
  - 
categories:
  - Development
  - Hacks
---

I figured this out trying to resize RRDs for Ganglia in a rrdcached-enabled environment, since expanding initial RRD parameters in gmetad doesn’t affect existing RRD files. Essentially you simply have to declare the RRA index and the expanded size, and this does the rest. rrdtool unfortunately doesn’t make it particularly easy to do this on a large scale, hence the scripting.

One-liner to expand RRDs:

    /etc/init.d/gmetad stop; /etc/init.d/rrdcached stop ; 
      find . | grep rrd | while read X; do fix-rrd.sh "$X"; done ; 
      /etc/init.d/rrdcached start ; /etc/init.d/gmetad restart
    

**fix-rrd.sh**:

    #!/bin/bash
    # fix-rrds.sh
    NEWRRDS="0:5856 1:20160 2:20160 3:52704 4:3740"
    for RRD in $*; do
            echo -n "Processing $RRD ... "
            for RRA in ${NEWRRDS}; do
                    A=$(echo $RRA | cut -d: -f1)
                    B=$(echo $RRA | cut -d: -f2)
                    echo -n "$RRA "
                    rrdtool resize "$RRD" $A GROW $B 
                            mv resize.rrd "$RRD" &#038;&#038; 
                            chown nobody "$RRD"
            done
            echo "done."
    done
