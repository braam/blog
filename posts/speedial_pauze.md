---
title: Speeddials with pauze
date: 2018-12-20
tags:
  - unify
layout: layouts/post.njk
---
To program a "dial pause" and DTMF changeover for suffix dialing of DTMF characters (e.g., for controlling voicemail boxes), you can use the Repdial "P-key" or "#" (pound) key. 

The repdial key for the customer must be set as: 
``` bash
<dial_number><dtmf_digit><pause_digit><access_code> e.g. 008007728477#P2210344
```
You can add as many P (pauzes) as you wish.
