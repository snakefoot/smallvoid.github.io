---
title: 'Fdisk with 64 GB support'
date: '2002-02-06T15:02:03+01:00'
permalink: /article/fdisk.html
author: Snakefoot
excerpt: 'Disk partitioning utility which is able handle hard disks larger than 64 GB.'
type: post
id: 81
categories:
    - ms-dos_utilities
tags:
    - fdisk
    - format
    - hard-disk-drive
    - partition
---
The FDISK delivered with MS-DOS 5 up to Win98 SE is not made to handle HDD beyond 64 GByte and shows the wrong size. To solve this Microsoft has released an updated version of <a href="https://www.bing.com/search?q=KB+263044+Q263044" title="Fdisk Does Not Recognize Full Size of Hard Disks Larger than 64 GB [Q263044]" rel="nofollow">fdisk.exe</a> ([Download Mirror](http://smallvoid.orgfree.com/?file=fdisk.zip)).  
  
 One can still use the original FDISK by creating one large drive, or several partitions using percentages (Not actual MByte size). FDISK will report the partition sizes wrong but they will be correct in DOS and Windows.  
  
 The FORMAT delivered with MS-DOS 5 up to WinMe is able to format partitions above 64 GByte. But visually it will show the wrong format size. <a href="https://www.bing.com/search?q=KB+263045+Q263045" rel="nofollow" title="Format Displays Size of Partitions or Logical Drives Larger Than 64 GB Incorrectly [Q263045]">MS KB263045</a>  
  
 Related [Pro and cons for using multiple partitions](/article/multiple-partitions.html)  
 Related [Partition Resizer](/article/partition-resizer.html)  
 Related [Delpart](/article/delpart.html)