---
layout: post
title: "Never write hasClass again"
date: 2013-06-27 19:09
comments: true
categories:
- jquery
---
```
$('.navigation').hasClass('collapsed');
```

The code above can be easily refactored into the both shorter and easier to read:
```
$('.navigation').is('.collapsed');
```