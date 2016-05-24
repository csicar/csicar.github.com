---
layout: post
title:  "Disable the Touchpad in Archlinux (on an T450s)"
date:   2016-04-16 12:29:00 +0100
categories: archlinux thinkpad
---

```bash
#!/bin/bash

device=`xinput | grep TouchPad | grep -o "id=.." | grep -o "[0-9]*"`
state=`xinput list-props "$device" | grep "Device Enabled" | grep -o "[01]$"`

if [ $state == '1' ];then
  xinput --disable $device
else
  xinput --enable $device
fi
```
