---
title: Myportal JAVA runtime issue
date: 2019-01-27
tags:
  - unify
  - MyPortal
layout: layouts/post.njk
---
Sometimes you install Myportal for Desktop but there is no java runtime installed at the workstation. So you go to <a href="www.ninite.com">www.ninite.com</a> and installs the necessary runtime. By using ninites you can install plugins/programs very fast without ads on other mess as a bonus you'll have java 32- and 64bit automatically installed. If for some reason after installing the required java runtime  MyPortal.jar still won't open, you have to set the java runtime location.

I tried everything to get this working within Windows but for some reason it wouldn't work. So I came up with the most simple method by changing the <b>MyPortal desktop shortcut</b> by adding <b>javaw -jar</b>:

``` js/2/4
Target: javaw -jar "C:\Program Files (x86)\CommunicationsClients\myPortal\myPortal.jar"
```

