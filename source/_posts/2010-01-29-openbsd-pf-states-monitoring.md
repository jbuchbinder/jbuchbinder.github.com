---
title: OpenBSD pf states monitoring
author: jeff
layout: post
permalink: /2010/01/29/openbsd-pf-states-monitoring/
categories:
  - Hacks
---
# 

The simple recipe is to add this to root’s cron:

`
* * * * * /usr/bin/gmetric -c /etc/gmond.conf -n pf_states -v $(/usr/local/sbin/pftop -b | grep pfTop | cut -d/ -f2 | cut -d, -f1) -t int32 -d 120 2>&#038;1 | logger -t pf_states
`

and install the **pftop** package along with a gmetric binary and a working **/etc/gmond.conf** configuration file. It might be advantageous to check for the maximum number of states as well.

In addition, you might want to know which pf rules are passing how much traffic. A nice easy way of doing this is to create this file as **./pfstates** (make it executable, of course):

    #!/usr/bin/perl
    # pfstates
    # jeff@ourexchange.net
    my $limit = shift  || 0;
     
    my $seg = 0;
    my @s = [];
    
    while (chomp( my $line = )) {
            $s[$seg] = $line;               
            if ($seg == 2) {
                    $seg = 0;
                    if ($s[1] !~ /States: 0/) {
                            my $states = 0;
                            if ($s[1] =~ m/States: (d )/) {
                                    $states = $1;
                            }
                            if ($states >= $limit) {
                                    print "[$states] $s[0]n";
                            }
                    }
            } else {
                    $seg  ;
            }
    }
    

…. then you would pipe pfctl’s state output to it:

    pfctl -v -s rules | ./pfstates
    

Optionally you could add a “minimum level” of connections you want to see:

    pfctl -v -s rules | ./pfstates 100
    

for example to see only rules passing 100 or more active connections.