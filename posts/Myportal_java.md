---
title: Disable or enable caller list on S5 handset
date: 2019-01-27
tags:
  - unify
  - MyPortal
layout: layouts/post.njk
---
Sometimes you install Myportal for Desktop but there is no java runtime installed at the workstation. So you go to <a href:"www.ninite.com">www.ninite.com</a> and installs the necessary runtime. By using ninites you can install plugins very fast without ads and java 64x will also installed automatically.
If for some reason after installing the required java runtime MyPortal.jar still wont open, you have to set the java runtime location. I tried everything to get this working within Windows but for some reason it wouldn't work.
So I came up with the most simple method by changing the MyPortal desktop shortcut by adding <b>javaw -jar</b>:

``` js/2/4
Target: javaw -jar "C:\Program Files (x86)\CommunicationsClients\myPortal\myPortal.jar"
```

