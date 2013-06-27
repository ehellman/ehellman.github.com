---
layout: post
title: "Multiple monitors on a Linux machine"
date: 2013-06-27 19:02
comments: true
categories:
- Linux
- Arch
---
I use this shell script to shoot up the screen of my 1005HA netbook to a 27" monitor.
<!-- more -->
It turns off the netbook display too since it's too small to use as either mirror, even extending the desktop to it would be a waste.

```
xrandr --output LVDS1 --off --output VGA1 --mode 1920x1080 --pos 0x0
```