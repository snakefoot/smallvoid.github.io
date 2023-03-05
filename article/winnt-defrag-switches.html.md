---
title: 'Defrag command line switches'
date: '2007-09-13T00:51:33+02:00'
status: publish
permalink: /article/winnt-defrag-switches.html
author: Snakefoot
excerpt: 'List of the available command line switches for defrag.'
type: post
id: 744
category:
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - command-line-switches
    - defrag
    - file-system
    - hard-disk-drive
    - partition
    - scheduled-task
post_format: []
tags:
    - 'defrag,hard-disk-drive,partition,command-line-switches,scheduled-task'
---
Defrag.exe is a command line tool included with Windows, which is quite useful when wanting to perform a scheduled [defragmentation](/article/defrag-hard-disk-partition.html) of the hard disk. There are several command line switches available when running the tool:

- Show available command line switches:
  > defrag -?
- Analysis of the partition to discover fragmentation level:
  > defrag c: -a
- Force defragmentation of the partition (Even if not having 15% free space available):
  > defrag c: -f
- Defragmentation of only the boot files on the partition:
  > defrag c: -b
- Display verbose information when displaying fragmentation statistics:
  > defrag c: -v

##### New commands in Vista

- Pause the defrag when the computer is not in idle state (Vista+):
  > defrag c: /i
- Complete defragmenation that includes all partitions (Vista+):
  > defrag /c
- Defrag all files independent of size. Performs by default a partial defragmentation excluding files larger than 64 MByte. (Vista+):
  > defrag c: /w

##### New commands in Win7

- Defrag all drives except those specified. (Win7+):
  > defrag c: /e
- Defrag using normal process priority, instead of low priority. (Win7+):
  > defrag c: /h
- Defrag each volume in parallel in the background. (Win7+):
  > defrag c: /m
- Defrag while printing progress information on the screen. (Win7+):
  > defrag c: /u
- Defrag with focus on free space consolidation, so there is contiguous free space for new files. (Win7+):
  > defrag c: /x
 
 Related [Logical Prefetcher helps defrag to optimize file layout](/article/winnt-logical-prefetcher.html)  
 Related [Repair the builtin disk defragmenter](/article/winnt-defrag-repair.html)  
 Related [Different defragmentation utilities available](/article/winnt-defrag-tools.html)  
  
 More Info [MS KB283080](http://support.microsoft.com/kb/283080 "Description of the New Command Line Defrag.exe Included with Windows XP [Q283080]")  
 More Info [Microsoft Windows XP - Defrag](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/defrag.mspx)  
  
 Credits [MaximumPCGuides.com](http://www.maximumpcguides.com/)