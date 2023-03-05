---
title: 'Configure the Recovery Log on stressed NTFS Volumes'
date: '2003-11-15T12:46:14+01:00'
status: publish
permalink: /article/winnt-ntfs-recovery-log.html
author: Snakefoot
excerpt: 'How to change the size of the NTFS transaction log to handle peak loads.'
type: post
id: 33
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - chkdsk
    - disk-performance
    - file-system
    - ntfs
    - recovery-log
    - transactionel
post_format: []
tags:
    - 'chkdsk,file-system,recovery-log,transactionel,ntfs,disk-performance'
---
The Windows NT File System (NTFS) uses transaction logging to ensure recoverability, thus making it a journal filesystem. When a user updates a file the Log File Service records all operations in a Recovery Log ($LogFile), so it can redo or undo the entire transaction in case of error. After a system crash (due to power failure or other cause), an analysis is performed of the damage and it is determined what operations to redo and undo according to the last check point.  
  
 The Log File Service commits the file operations every now and then and makes a checkpoint. If there are many concurrent transactions (Disk Activity) and the disk system cannot keep up, then the Log File Service will fall behind and the Recovery Log becomes full. The Log File Service will then block for new file operations while it commits the operations contained in the Recovery log to the disk. This blocking will reduce performance significantly.  
  
 If experiencing reduced performance when the computer is under stress, then one can check if it caused by a full Recovery Log:

- Configure **Performance Logs and Alerts** to monitor the activity of the **Current Disk Queue Length** counter for desired **PhysicalDisk** object.
- Observe if the **Current Disk Queue Length** is constantly high with intermittent drops to exactly 1
 
 The normal solution for this situation is to upgrade the disk system or to divide the load to several disks. If the problem only occurs once in a while, then a temporary solution could be to increase the size of the Recovery Log, so it takes a longer time before it becomes full.  
  
 To see the current size of the Recovery Log for an NTFS partition:
 > CHKDSK &lt;Drive:&gt; /L

 To change the size (KBytes) of the Recovery Log for an NTFS partition:
 > CHKDSK &lt;Drive:&gt; /L:65536 /F

 More Info [MS KB101670](http://support.microsoft.com/kb/101670 "Transaction Log Supports NTFS Recoverability [Q101670]")  
  
 Credits [www.jsifaq.com](http://www.jsifaq.com/)