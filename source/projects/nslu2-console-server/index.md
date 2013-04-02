---
title: NSLU2 Console Server
author: jeff
layout: page
---
# 

### Server Setup

Install [SlugOS/BE][1] with:  
• USB hub  
• USB/serial adapter attached to F-F 9 port RS232 cable

 [1]: http://www.nslu2-linux.org/wiki/SlugOS/SlugOSBE

Install serial support:  
`
root@BOS-ts1:/$ ipkg update
Downloading http://ipkg.nslu2-linux.org/feeds/slugosbe/cross/4.8-beta/Packages.gz
Inflating http://ipkg.nslu2-linux.org/feeds/slugosbe/cross/4.8-beta/Packages.gz
Updated list of available packages in /var/lib/ipkg/cross
Downloading http://ipkg.nslu2-linux.org/feeds/slugosbe/native/4.8-beta/Packages.gz
Inflating http://ipkg.nslu2-linux.org/feeds/slugosbe/native/4.8-beta/Packages.gz
Updated list of available packages in /var/lib/ipkg/native
root@BOS-ts1:/$ ipkg install kernel-module-pl2303
Installing kernel-module-pl2303 (2.6.21.7 svnr927-r0) to root...
Downloading http://ipkg.nslu2-linux.org/feeds/slugosbe/cross/4.8-beta/kernel-module-pl2303_2.6.21.7 svnr927-r0_nslu2be.ipk
Installing kernel-module-usbserial (2.6.21.7 svnr927-r0) to root...
Downloading http://ipkg.nslu2-linux.org/feeds/slugosbe/cross/4.8-beta/kernel-module-usbserial_2.6.21.7 svnr927-r0_nslu2be.ipk
Configuring kernel-module-pl2303
Configuring kernel-module-usbserial
root@BOS-ts1:/$
`

Install picocom:  
`
root@BOS-ts1:/$ ipkg install picocom
Installing picocom (1.4-r2) to root...
Downloading http://ipkg.nslu2-linux.org/feeds/slugosbe/cross/4.8-beta/picocom_1.4-r2_armv5teb.ipk
Configuring picocom
root@BOS-ts1:/$
`

picocom syntax:  
`
root@BOS-ts1:/$ picocom --help
picocom v1.4
Usage is: picocom [options] 
Options are:
  --aud 
  --low s (=soft) | h (=hard) | n (=none)
  --arity o (=odd) | e (=even) | n (=none)
  --atabits 5 | 6 | 7 | 8
  --scape 
  --nonit
  --noeset
  --noock
  --end-cmd 
  --receie-cmd 
  --elp
< ?> indicates the equivalent short option.
Short options are prefixed by "-" instead of by "--".
root@BOS-ts1:/$
`

Console server scripts:

    root@BOS-ts1:~$ cat /etc/port.config 
    1:sw2:9600
    2:poeswitch:9600
    3:sw1:9600
    4:fw:9600
    7:pbx:57600
    root@BOS-ts1:~$ cat /usr/bin/consolesh 
    #!/bin/sh
    
    done=0
    
    while [ $done -eq 0 ]; do
            clear
            echo "Welcome to $(hostname)"
            echo "Console Server"
            echo "  Uptime  :       $(uptime | cut -d, -f1 | cut -d' ' -f4-)"
            echo "  IP      :       $( /sbin/ifconfig eth0 | grep 'inet addr' | cut -d: -f2 | cut -d' ' -f1 )"
            echo ""
            echo "Connected ports:"
            ls /dev/ttyUSB* 2>&#038;1 | grep -v no | cut -dB -f2 | while read P; do
                    D=$(cat /etc/port.config | grep -E "^$(( $P   1 )):" | cut -d: -f2)
                    echo "  Port $(($P   1))        :       $D"
            done
            echo ""
            echo -n "Please choose a port number to access, or '#' for shell --> "
            read PORT
            if [ "$PORT" == "" ]; then
                    exit
            fi
            if [ "$PORT" == "#" ]; then
                    echo "Spawning shell, type 'exit' to leave"
                    sh
            else
                    SPEED=$( cat /etc/port.config | grep -E "^${PORT}:" | cut -d: -f3 )
                    /usr/bin/serial.sh $PORT $SPEED
    	fi
    done
    
    exit
    
    root@BOS-ts1:~$ cat /usr/bin/serial.sh 
    #!/bin/sh
    if [ $# -ne 2 ]; then
    	echo "syntax: $0 portnumber speed"
    	exit
    fi
    PORT=$(( $1 - 1 ))
    echo "Escape sequence is Ctrl-A Ctrl-X"
    picocom -b $2 -f h -p n -d 8 -r /dev/ttyUSB${PORT}
    root@BOS-ts1:~$
    

Final setup:  
After you’ve copied your keys over, set root’s shell to be /usr/bin/consolesh

### Client Setup

#### BIOS

    ---------------------------------------------------- 
    |               Console Redirection                  |
    |----------------------------------------------------|
    |                                                    |
    |   Com Port Address           [On-board COM A]      |
    |                                                    |
    |   Console connection:        [Direct]              |
    |   Baud Rate                  [9600]                |
    |   Flow Control               [None]                |
    |   Console Type               [vt100]               |
    |   Continue C.R. after POST:  [On]                  |
     ---------------------------------------------------- 
    

#### OpenBSD

/etc/ttys:

Change:

    tty00   "/usr/libexec/getty std.9600"   unknown off
    

to:

    tty00   "/usr/libexec/getty std.9600"   vt100   on secure
    

/etc/boot.conf:

Create and/or edit file and add the following:

    stty com0 9600
         set tty com0
    

Note: Only the first serial port (com0) is supported for console on amd64 and i386.

#### CentOS/Linux

The console needs to be redirected: Grub, Xen, Linux & Getty.

/boot/grub/grub.conf:

    # Remove splash line
    
    # Serial console for grub
    serial --unit=0 --speed=9600 --word=8 --parity=no --stop=1
    terminal --timeout=5 serial console
    
    title...
    
       # Serial console for XEN
       kernel /xen.gz..... com1=9600,8n1 console=com1,vga
    
       # Serial console for Linux
       module /vmlinuz-... console=tty0 console=ttyS0,9600n8
    

Create console login:

/etc/securetty:

Add:

    ttyS0
    

/etc/inittab:

Add:

    co:2345:respawn:/sbin/agetty -L 9600 ttyS0 vt100-nav
    

## Alternate Method

You can also use [conman]() (Console Manager) to do the same thing. I have an NSLU2 package available here:  
[http://www.mediafire.com/file/tzkmt9jnnyx/conman\_0.2.3-1\_armeb.ipk][2].

 [2]: http://www.mediafire.com/file/tzkmt9jnnyx/conman_0.2.3-1_armeb.ipk