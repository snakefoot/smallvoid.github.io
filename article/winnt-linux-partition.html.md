---
title: 'Mount Ext2 / Ext3 linux partitions inside Windows'
date: '2007-08-28T02:02:29+02:00'
status: publish
permalink: /article/winnt-linux-partition.html
author: Snakefoot
excerpt: 'Access Linux Ext2 / Ext3 partitions inside Microsoft Windows.'
type: post
id: 732
category:
    - Utilities
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag:
    - drive-mount
    - ext2
    - ext3
    - file-system
    - hard-disk-drive
    - linux
    - partition
post_format: []
tags:
    - 'linux,hard-disk-drive,partition,ext3,ext2,drive-mount'
---
[Ext2 Installable file system (Ext2IFS / Ext2fs)](http://www.fs-driver.org/) is a file system device driver, which allows reading and writing of Linux partitions formatted as Ext2 / Ext3, and mount them inside Windows like they were normal FAT / NTFS partitions.
- Note Ext3 is pretty much Ext2 with journal support, so unless accessing a Ext3 partition with uncommitted journal entries (improper shutdown), then Ext3 partitions can be accessed like a Ext2 partition.
 
[Ext2fsd](http://ext2fsd.sourceforge.net/) is also a Ext2 file system device driver, which acts as an extension to mount Ext2 partitions from within Windows and read and write files on the partition, and beginning support for Ext3 journaling (Open source and can also be used on Vista).  
  
[Explore2fs](http://www.chrysocome.net/explore2fs) cannot map Ext2 volumes as normal drive letters, but is a GUI explorer tool for browsing Ext2 partitions within Windows. They are also working on [Virtual Volumes](http://www.chrysocome.net/virtualvolumes) that will make it possible to mount Ext2 (and other partition formats like LVM and ReiserFS) inside Windows (Still BETA).  
  
[DiskInternals Linux Reader](http://www.diskinternals.com/linux-reader/) is a GUI explorer for browsing Ext2 / Ext3 partitions, which can be used to access files on Linux partitions inside Windows.