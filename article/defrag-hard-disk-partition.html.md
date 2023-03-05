---
title: 'Defrag hard disk partitions to speed up file operations'
date: '2000-01-01T23:52:51+01:00'
status: publish
permalink: /article/defrag-hard-disk-partition.html
author: Snakefoot
excerpt: 'List of steps to perform before starting a file defragmentation on a hard disk partition.'
type: post
id: 130
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - defrag
    - disk-performance
    - file-system
    - hard-disk-drive
post_format: []
tags:
    - 'defrag,hard-disk-drive,disk-performance'
---
A partition consist of a long chain of [clusters](/article/cluster-hard-disk-partition.html). When a new file is created, then Windows searches the partition to find a subchain of free clusters, which is large enough to contain the entire file. If no cluster-chain is large enough, then the file is fragmented over several smaller chains of clusters.  
  
 It will take longer time to read a whole file when it is fragmented, because the HDD has to make several seeks to read all the cluster-chains that contains the file. Defragmentation Tools will try to rearrange the data of the fragmented files so the file is contained in a single cluster-chain.  
  
 Checks before starting defragmentation of a partition :

- Scan the partition for errors (Using Scandisk or Chkdsk /f).
- Empty directory with temporary files which might reside on the partition (Recycle Bin, [Temporary Internet Files](/article/ie-temporary-internet-files.html), [TMP](/article/temporary-directory.html)).
- Make sure there is enough free space on the partition to move files around (15 %).
- Stop any unnecessary programs that writes to the partition (Ex. filesharing programs).
- Disable any screen saver which might take all the resources from the defrag process.
 
 Note after a defragmentation of a partition, some files might still be fragmented. This is usual either very large files or files which are changing in size constantly, so the gain of defragmenting these types of files completely is minimal.  
  
 Note a new feature was added with Windows 98/Windows XP, which monitors the launch of applications. The defragmenter uses this information to group the files used by the application close together to minimize seek time.
- Win98/WinMe - [Configure monitoring of application startup](/article/win9x-application-log.html)
- WinXP - [Configure the logical prefetcher](/article/winnt-logical-prefetcher.html)