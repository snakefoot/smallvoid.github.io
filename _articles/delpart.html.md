---
title: Delpart
date: '2003-02-22T15:58:52+01:00'
permalink: /article/delpart.html
author: Snakefoot
excerpt: 'Can delete a NTFS partition from DOS.'
type: post
id: 85
categories:
    - ms-dos_utilities
tags:
    - fdisk
    - ntfs
    - partition
---
[FDISK](/article/fdisk.html) is not completely compatible with NTFS partitions, which causes it to mess up when deleting non-primary NTFS partitions.
> Cannot delete Extended DOS Partition while logical drives exist  
>   
>  No Logical Drives defined

 To make up for that Microsoft created the utility [Delpart.exe](http://smallvoid.orgfree.com/?file=delpart.zip) ([Download Mirror](ftp://ftp.microsoft.com/bussys/winnt/winnt-public/reskit/nt31/i386/RESKIT.EXE)), which makes it possible to delete logical NTFS partitions within an extended partition without deleting the wrong partitions.  
  
 More info <a href="https://www.bing.com/search?q=KB+261473+Q261473" rel="nofollow" title="Unable to Delete a Partition or Logical DOS Drive Using the Fdisk Utility [Q261473]">MS KB261473</a>  
 More info <a href="https://www.bing.com/search?q=KB+310359+Q310359" rel="nofollow" title="Cannot View NTFS Logical Drive After Using Fdisk [Q310359]">MS KB310359</a>  