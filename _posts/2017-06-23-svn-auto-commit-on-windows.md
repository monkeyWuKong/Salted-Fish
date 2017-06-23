---
layout: post
title: "svn auto commit on windows"
comments: true
description: "notes"
keywords: "scripts notes"
---


## bat script

```
SET WORKING_COPY=F:\CodeX\proj
svn update %WORKING_COPY%
svn ci %WORKING_COPY%\proj1\* %WORKING_COPY%\proj2\* -m "auto commit"
msg "wait"

```

then set a Mouse Gesture by software [Just Gestures](http://www.justgestures.com/)

done.