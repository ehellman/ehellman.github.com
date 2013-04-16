---
layout: post
title: "Reset Network Interface Naming Convention In Linux"
date: 2013-04-15 22:32
comments: true
categories:
- Linux
- Arch
---
I ran into this problem today on my old laptop that runs Arch. My network interfaces didn't have persistent names, my wired network interface was called `enp1s0` and my wireless `wlp2s0`, and when I plugged in an external WiFi dongle it named something like `wlp0s2s7su8sau` ... or something like that. By no means am I an expert, but I finally managed to solve this problem.
<!-- more -->
Here's how I did it:
```
$ ln -s /dev/null /etc/udev/rules.d/80-net-name-slot.rules
```

This did the trick for me! After a reboot, ifconfig showed me: `eth0`, `lo` and `wlan0`, just the way I like it.

Another way to display all the network interfaces is to type:
```
$ ls /sys/class/net
```

Want to know more? This link explain why it's like this, and also includes the solution above:
http://www.freedesktop.org/wiki/Software/systemd/PredictableNetworkInterfaceNames