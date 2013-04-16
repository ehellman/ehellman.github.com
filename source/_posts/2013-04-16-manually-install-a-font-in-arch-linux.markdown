---
layout: post
title: "Manually install a font in Arch Linux"
date: 2013-04-16 15:56
comments: true
categories:
- Linux
- Arch
---
Installing a font manually is something that I always used to forget how to do since most of the fonts that I installed I got through either yaourt or some other package manager.
<!-- more -->
Unpack the file and move it to the shared fonts folder
```
$ mv font.ttf /usr/share/fonts/
```

Or if you want to install the font for a single user, move it to the `.fonts` directory in the home folder.
```
$ mv font.ttf ~/.fonts/
```

You might also have to update `/etc/X11/xorg.conf` or `/etc/xorg.conf` with the new directory. Search for `FontPath` to find the correct location within the file to add your new path.

Now, reload the font cache:
```
$ fc-cache -vf
```