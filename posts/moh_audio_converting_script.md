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

For Windows user you need to download ffmpeg.exe and place it inside the Windows folder.
``` js/2/4
32-bit: C:\windows\system32
64-bit: C:\windows\syswow64
´´´
Now create a batch file and place following script inside it, you can to convert the files drag and drop them on the script (or on a shortcut to the script).
``` js/2/4
echo off
:again
ffmpeg.exe -i "%~1" -acodec pcm_s16le -ac 1 -ar 8000 "%~p1%~n1.wav"
shift
if "%~1" == "" goto:eof
goto:again
´´´
