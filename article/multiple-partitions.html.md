---
title: 'Pro and cons for using multiple disk partitions'
date: '2002-07-06T12:11:01+02:00'
status: publish
permalink: /article/multiple-partitions.html
author: Snakefoot
excerpt: 'Describes the benefits and the costs of using multiple partitions.'
type: post
id: 72
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - fat16
    - fat32
    - fdisk
    - ntfs
    - partition
post_format: []
tags:
    - 'fat16,fat32,ntfs,partition,fdisk'
---
Disk partitioning is a personal thing, and every person have their favorite setup. But here are the reasons for me to use several partitions.  
  
 Pro :

- Reformatting will not delete your personal data when it placed on a different partition than the operating system
- [Temporary files](/article/windows-temporary-files.html) will not cause [file fragmentation](/article/defrag-hard-disk-partition.html), when it is placed on a separate partition.
- Dual booting operating systems will not interfere with each other, when each operating system is placed on separate primary partitions
- Enables organization of your data on a level beyond directories.
- The outer edge of the HDD has the best performance, by creating a partition here, then it is possible to manually decide what files should have the best file-performance. (Defragmentation tools solves this automatically)
- Faster access to files and directories, when using FAT16/32 on large partition the File Allocation Table(FAT) will become extremely large and slow to search through (NTFS can solve this, though one should only use 85% of the partition)
- Less slack with small files, when using FAT16/32 the cluster-size can become quite big, causing a small file to use a lot more space than its actual size (NTFS can solve this)
- Defragmentation is not required for the entire HDD, when having several partition only have to defragment the partition where files are often create/deleted
- Gives a little more security, incase the File Allocation Table (FAT/MFT) on one partition is corrupted, then it will not affect the other partitions. (Backup solves this)
 
 Cons :
- File copy/move between partitions on the same HDD is extremely slow
- One can still organize data by using folders.
- Partitions are less dynamic than folders, thus one can reach the partition limit even though there is still plenty of space on the HDD. (Though one can use [Partition Magic](http://www.powerquest.com/partitionmagic/) to resize the partition)
- The HDD is forced to make a long seek when accessing a file on another partition
 
 The built-in partition tool in DOS is [FDISK](/article/fdisk.html).  
  
 More Info [Bob Watson - FDISK Tutorial](http://home7.inet.tele.dk/batfiles/msdos7/index.htm?cmdindex.htm&fdisk1.htm "Using FDISK - The Screens")  
 More Info [FDISK Simulation](http://www.computerhope.com/sfdisk1.htm "Helping you with the FDISK MS-DOS command by providing screen shots")  
 More Info [MS KB255867](http://support.microsoft.com/kb/255867 "How to Use the Fdisk Tool and the Format Tool to Partition or Repartition a Hard Disk [Q255867]")