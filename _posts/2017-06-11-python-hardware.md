---
layout: post
title: "python hardware"
comments: true
description: "notes on python-hardware module"
keywords: "python27, hardware, linux, disk"
---

# python hardware

## 简介

目标： 获取linux服务器的硬件信息，如硬盘信息等。

环境: 

>centos 7.2 (1511)

>python 2.7

## 安装

`pip install hardware`

依赖： `yum install hdparm`

## 使用

查看可用的方法：

```
Python 2.7.5 (default, Nov 20 2015, 02:00:19) 
[GCC 4.8.5 20150623 (Red Hat 4.8.5-4)] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import hardware
>>> help(hardware)
Help on package hardware:

NAME
    hardware - # -*- coding: utf-8 -*-

FILE
    /usr/lib/python2.7/site-packages/hardware/__init__.py

PACKAGE CONTENTS
    benchmark (package)
    cardiff (package)
    cmdb
    detect
    detect_utils
    diskinfo
    generate
    hpacucli
    infiniband
    ipmi
    matcher
    megacli
    state
    tests (package)

DATA
    __version__ = '0.18.0'

VERSION
    0.18.0
```

获取硬盘列表：

```
>>> from hardware import diskinfo
>>> disks = diskinfo.disknames()
>>> disks
['sda', 'sdb', 'sdc', 'sdd', 'sde', 'sdf', 'sdg', 'sdh', 'sdi', 'sdj', 'sdk', 'sdl']
```

获取容量信息：

```
>>> disknames
['sda', 'sdb', 'sdc', 'sdd', 'sde', 'sdf', 'sdg', 'sdh', 'sdi', 'sdj', 'sdk', 'sdl']
>>> sizes = diskinfo.disksizes(disknames)
>>> sizes
{'sdd': 999, 'sde': 999, 'sdf': 999, 'sdg': 999, 'sda': 999, 'sdb': 999, 'sdc': 999, 'sdl': 999, 'sdh': 999, 'sdi': 999, 'sdj': 999, 'sdk': 999}
```

