---
layout: post
title: "pandoc files from markdown to restructuredtext"
comments: false
description: "notes"
keywords: "programming notes script"
---

## steps

you have many markdown files, put trans.py and start.bat in your path.

trans.py:

```
import os

#os.system('pandoc --help')

cur_dir = os.getcwd()

files = os.listdir(r'./')

for file in files:
    if len(file) < 3:
        continue

    if file[-2:] != 'md':
        continue
    file_name = file[:-3]

    print file_name

    cmd = 'pandoc -f markdown -t rst -o %s.rst %s' % (file_name, file)

    os.system(cmd)

print 'ok'
```

use a `start.bat` to run py:

`python trans.py`