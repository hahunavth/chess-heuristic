#!/bin/bash1

I had the same issue with `GLIBCXX_3.4.29' not found.

First you should check if you can see GLIBCXX_3.4.29 in your conda lib:
strings ~/miniconda3/lib/libstdc++.so.6 | grep GLIBCXX_3.4.2
If not you should check if it exists in your systems lib:
strings /lib/libstdc++.so.6 | grep GLIBCXX_3.4.2
If this shows the version you can simply copy the file from the /lib to the miniconda3/lib with:
copy /lib/libstdc++.so.6 ~/miniconda3/lib/
but also check where the lib folder is located in your miniconda environment!
