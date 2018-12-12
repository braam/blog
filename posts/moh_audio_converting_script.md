---
title: MOH / audio converting script
date: 2018-12-12
tags:
  - unify
  - linux
layout: layouts/post.njk
---
I find myself doing the same thing over and over again when converting audio files to use for MOH or announcements in the call flow.
That's why I created this script to use as an alias in my bash shell, it uses ffmpeg as external application.

``` js/2/4
function wavPABX {
 if [ -z "$1" ]; then
    # display usage if no parameters given
    echo "Usage: wavPABX <path/file_name>.<mp3|m4a|wav|..."
    echo        "wavPABX <path/file_name_1.ext> [path/file_name_2.ext]"
 else
    for n in $@
    do
      if [ -f "$n" ] ; then
          ffmpeg -i "$n" -acodec pcm_s16le -ac 1 -ar 8000 _$n
      else
          echo "'$n' - file does not exist"
          return 1
      fi
    done
 fi
}
```
