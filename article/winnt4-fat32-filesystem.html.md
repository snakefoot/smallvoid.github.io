---
title: 'FAT32 file system driver for Windows NT4'
date: '2000-01-01T13:58:11+01:00'
status: publish
permalink: /article/winnt4-fat32-filesystem.html
author: Snakefoot
excerpt: 'SysInternals has created a FAT32 driver that allow one to mount and access FAT32 partitions.'
type: post
id: 490
category:
    - Utilities
tag:
    - drive-mount
    - fat32
    - partition
post_format: []
tags:
    - 'fat32,partition,drive-mount'
---
Windows NT 4.0 doesn't have native FAT32 support, but with [FAT32NT](http://www.sysinternals.com/Utilities/Fat32.html) it is possible to mount and get access to your FAT32 partitions.  
  
 Note it is probably best not to perform [file defragmentation](/article/defrag-hard-disk-partition.html) in WinNT 4.0 on a FAT32 partition. It is better to use Win2k/Win9x own defragger on FAT32 drives.  
  
 Note in Win2k+ FAT32 is fully supported, with the limitation that it won't create or format FAT32 partitions larger than 32 GB.