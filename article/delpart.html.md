---
title: Delpart
date: '2003-02-22T15:58:52+01:00'
status: publish
permalink: /article/delpart.html
author: Snakefoot
excerpt: 'Can delete a NTFS partition from DOS.'
type: post
id: 85
category:
    - Utilities
tag:
    - fdisk
    - ntfs
    - partition
post_format: []
tags:
    - 'ntfs,partition,fdisk'
---
[FDISK](/article/fdisk.html) is not completely compatible with NTFS partitions, which causes it to mess up when deleting non-primary NTFS partitions. > Cannot delete Extended DOS Partition while logical drives exist  
>   
>  No Logical Drives defined

 To make up for that Microsoft created the utility [Delpart.exe](http://smallvoid.orgfree.com/?file=delpart.zip) ([Download Mirror](ftp://ftp.microsoft.com/bussys/winnt/winnt-public/reskit/nt31/i386/RESKIT.EXE)), which makes it possible to delete logical NTFS partitions within an extended partition without deleting the wrong partitions.  
  
 More info [MS KB261473](http://support.microsoft.com/kb/261473 "Unable to Delete a Partition or Logical DOS Drive Using the Fdisk Utility [Q261473]")  
 More info [MS KB310359](http://support.microsoft.com/kb/310359 "Cannot View NTFS Logical Drive After Using Fdisk [Q310359]")  