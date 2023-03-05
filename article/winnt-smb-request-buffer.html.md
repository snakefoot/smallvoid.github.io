---
title: 'Configure the file server request buffer size'
date: '2001-01-01T23:19:07+01:00'
status: publish
permalink: /article/winnt-smb-request-buffer.html
author: Snakefoot
excerpt: 'Increasing the request buffer size can improve file sharing performance on high latency networks.'
type: post
id: 439
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - microsoft-network
    - network-performance
post_format: []
tags:
    - 'network-performance,microsoft-network'
---
The Server service creates a request buffer for each smb session, the client will not attempt to send more requests than the server request buffer can hold. If working on a high latency network then it can increase file server performance if it has a large request buffer, but it will then use more non-paged pool memory for each smb session.  
  
 The request buffer size is configured with this DWORD registry key:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  SizReqBuf = 17424 (Default=4356 Bytes, More than 512 MB RAM=16384 Bytes, Range 1024-65536)

 Note Windows NT4 does not have complete Large File (CAP\_LARGE\_FILE) support, which introduce the following behavior:
- Win2k/Win2k3 uses the CAP\_LARGE\_WRITEX smb request (60K buffer size) when copying a file to a remote computer. WinNT4 doesn't support this request and instead uses the request buffer (4K buffer size), which will make the file transfer slow. Increasing the request buffer size of Windows NT4 will make it faster at receiving files.
- Copying files from WinNT4 to Win2k/Win2k3 is fast because WinNT4 supports the smb request CAP\_LARGE\_READX.
- WinNT4 to WinNT4 file transfers uses CAP\_RAW\_MODE (64K buffer size), which is fast.
 
 Note Windows NT4 used as a print server will also perform better by increasing the request buffer size. It will make the transfer of the print job to the WinNT4 faster.  
  
 Note if using a large CORE SMB buffer and at the same time making small requests (Directory listings), then [delayed ACK](/article/winnt-nagle-algorithm.html) might cause low performance.  
  
 More info [MS KB123819](http://support.microsoft.com/kb/123819 "File Manager I/O Optimizations Slow other File Transfers [Q123819]")  
 More info [MS KB151996](http://support.microsoft.com/kb/151996 "How to Improve Data Transfers over RAS, RRAS, or Slow Links [Q151996]")  
 More info [MS KB152081](http://support.microsoft.com/kb/152081 "Use of Raw Data Transfer Mode Influenced by Application [Q152081]")  
 More info [MS KB177266](http://support.microsoft.com/kb/177266 "Remote Directory Lists Are Slower Than Local Directory Listings [Q177266]")  
 More info [MS KB223140](http://support.microsoft.com/kb/223140 "SMB Block Size Negotiation When Copying Files with Windows NT Explorer [Q223140]")  
 More info [MS KB279282](http://support.microsoft.com/kb/279282 "Slow File Write from Windows 2000 to Windows NT 4.0 Server [Q279282]")  
 More info [MS KB320829](http://support.microsoft.com/kb/320829 "HOW TO: Modify the Default SizReqBuf Value in Windows 2000 [Q320829]")  