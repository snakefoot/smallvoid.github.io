---
title: 'Configure opportunistic locking for files on network shares'
date: '2005-06-23T22:31:39+02:00'
status: publish
permalink: /article/winnt-network-opportunistic-locking.html
author: Snakefoot
excerpt: 'Opportunistic locking delivers good network performance but older implementations can lead to data loss.'
type: post
id: 446
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - network-share
    - opportunistic-locking
post_format: []
tags:
    - 'opportunistic-locking,network-share'
---
When accessing a file on the network, then the file operations are converted to network requests and replies. To minimize the amount of network request and replies it is best to read/write in large blocks (64K), but many applications only read/write a single byte at the time, thus generating a large amount of network traffic.  
  
 Opportunistic locking (OpsLocks) is a way to help such applications, by implementing a read ahead and a lazy write cache. The client requests a read or write lock on the file, when they are granted the lock, then the client caches the file locally so sequent read/write operations from the application only affects the cache. If another client requests a read or write lock on the file, and it conflicts with an existing opportunistic lock, then the opportunistic lock is broken (Caches are flushed), and instead the access for all clients will revert to network requests/replies.  
  
 Note if working with files over a non-reliable connection or non-reliable fileserver, then opportunistic locking will most likely cause the client application to loose any changes made to the file without closing the file.  
  
 To configure the use of opportunistic locking for a Windows NT4 client:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanWorkstation \\Parameters\]  
>  UseOpportunisticLocking = 1 (Default = 1)

 To configure the use of opportunistic locking for a Windows 2000/XP client:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\MrXSmb \\Parameters\]  
>  OplocksDisabled = 0 (Default = 0)

 To configure the use of opportunistic locking for the server:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  EnableOplocks = 1 (Default = 1)

 To configure the use of byte-range locking that allows a client to only lock portions of a read-only file, but at the cost of updating the lock continuously (WinXP/Win2k3):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanWorkstation \\Parameters\]  
>  DisableByteRangeLockingOnReadOnlyFiles = 1 (Default = 0)

 Note if using Windows NT 4.0 or Windows 2000 SP2 (Or previous), then one should consider disabling opportunistic locking as it doesn't work properly.  
  
 Note Windows Vista can only disable opportunistic locking for traditional SMB (SMB1), but not for SMB2. If disabling opportunistic locking, then the [offline files feature](/article/winnt-services-cscservice.html) will fail.  
  
 More Info [MS KB129202](http://support.microsoft.com/kb/129202 "PC Ext: Explanation of Opportunistic Locking on Windows NT [Q129202]")  
 More Info [MS KB224992](http://support.microsoft.com/kb/224992 "Maintaining Transactional Integrity with OPLOCKS [Q224992]")  
 More Info [MS KB296264](http://support.microsoft.com/kb/296264 "Configuring Opportunistic Locking in Windows [Q296264]")  
 More Info [MS KB306981](http://support.microsoft.com/kb/306981 "Level II Oplocks Are Not Granted After a File Is Locked [Q306981]")  
 More Info [MS KB818396](http://support.microsoft.com/kb/818396 "File Operation Takes 35 Seconds or Longer on a Down-Level Server Running an SMB Service [Q818396]")  
 More Info [MSDN: Opportunistic Locks](http://msdn.microsoft.com/library/en-us/fileio/fs/opportunistic_locks.asp)  