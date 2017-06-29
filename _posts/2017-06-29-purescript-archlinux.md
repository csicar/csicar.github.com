---
layout: post
title:  "Insalling Purescript under Archlinux"
date:   2017-06-29 19:5:00 +0100
categories: archlinux purescript
---

1. download the binary for linux
----

```bash
$ wget https://github.com/purescript/purescript/releases/download/v0.11.5/linux64.tar.gz - /opt/purescriptw
```

2. smylink the executable
---
```bash
$ ln -s /opt/purescript/purs /usr/local/bin/purs
```

3. install libtinfo
---
```bash
$ gpg --keyserver pgp.mit.edu --recv-keys F7E48EDB # needed for the folloing package
$ pacaur -S ncurses5-compat-libs
$ pacaur -S libtinfo
```
see
[here](https://www.adlerweb.info/blog/2017/02/01/arch-linux-arduino-libtinfo-so-5-fehlt)
