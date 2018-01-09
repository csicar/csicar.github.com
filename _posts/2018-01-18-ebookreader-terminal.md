---
layout: post
title:  "Access Terminal on PocketBook Touch Lux 2"
date:   2018-01-18 19:50:00 +0100
categories: pocketbook linux root
---

UART Interface
----


![pocketbook PCB]({{ site.url }}/assets/img/pb.jpg)

Connect:

PB | UART Interface
-- | ----
GND | GND
TX | RX
RX | TX

### Find the right tty device

1. run command and connect UART converter:

```bash
> dmesg --follow
....
[...] ...: ... new attached to ttyUSB0
```

### connect to uart

BAUD-Rate: 115200

```bash
> screen /dev/ttyUSB0 115200
```

after:
```
< HTTP/1.1 200 OK
< Date: Tue, 09 Jan 2018 15:20:21 GMT
< Server: Apache/2.2.3 (CentOS)
< X-Powered-By: PHP/5.3.18
< Cache-Control: no-cache
< Transfer-Encoding: chunked
< Content-Type: application/json
< 
[]
cleanup task 'pbpn_broker.app' (1329)
``` 
press `enter` a few times.

### on the machine

```bash
~ # help
Built-in commands:
------------------
        . : [ [[ bg break cd chdir continue echo eval exec exit export
        false fg getopts hash help history jobs kill local printf pwd
        read readonly return set shift source test times trap true type
        ulimit umask unset wait
~ # 
[               free            ln              pwdx            timeout
arp             fsck            losetup         reboot          tinysmbd
ash             fsync           ls              renice          top
awk             fuser           lsmod           reset           touch
base64          getopt          lsof            rfcomm          tr
basename        grep            lsusb           rm              traceroute
bunzip2         groups          lzma            rmdir           true
busybox         gunzip          lzop            rmmod           tty
bzcat           gzip            mattr           route           tune2fs
bzip2           halt            md5sum          rtcwake         udhcpc
cat             hciattach       mdev            rz              udhcpc.sh
catv            hciconfig       mkdir           sdpd            udhcpd
chat            hcitool         mke2fs          sdptool         uiquery.app
chgrp           hd              mkfifo          sed             umount
chmod           head            mkfs.ext2       set_bootmode    uname
chown           hexdump         mkfs.ext3       setconsole      uniq
chroot          hostname        mkfs.vfat       setlogcons      unix2dos
cksum           hotplug         mknod           setserial       unlzma
clear           httpd           mktemp          setsid          unlzop
conspy          hwclock         modprobe        sh              unzip
cp              hwconfig        more            sha1sum         uptime
cut             id              mount           shutdown        usleep
date            ifconfig        mv              sleep           uudecode
dd              ifdown          nc              smemcap         uuencode
df              ifup            netstat         sort            vi
dirname         init            nice            split           watch
dmesg           insmod          nohup           stat            watchdog
dos2unix        ionice          nslookup        strace          wc
dropbear        iostat          ntpd            strings         wget
du              ipcrm           oftpd           stty            which
echo            ipcs            pgrep           su              whoami
egrep           iwconfig        pidof           suspend         wl
env             iwevent         ping            switch_root     wpa_cli
expand          iwgetid         pivot_root      swupdate        wpa_passphrase
expr            iwlist          pkill           sync            wpa_supplicant
false           iwpriv          pmap            sysctl          xargs
fdisk           iwspy           poweroff        tail            yes
fgrep           kill            printf          tar             zcat
find            killall         ps              tee
flock           length          pstree          test
fold            less            pwd             time
```

#### Start ssh server:

`192.168.2.100` stands for the IP-Address from that you want to access the PocketBook

```bash
~ # dropbear -B -G 192.168.2.100
[1445] Jan 01 01:35:03 Failed loading /etc/dropbear/dropbear_dss_host_key
[1445] Jan 01 01:35:03 Failed loading /etc/dropbear/dropbear_ecdsa_host_key
~ # [1450] Jan 01 01:35:03 Running in background
```