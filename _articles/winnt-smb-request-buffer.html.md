---
title: 'Configure the file server request buffer size'
date: '2001-01-01T23:19:07+01:00'
permalink: /article/winnt-smb-request-buffer.html
author: Snakefoot
excerpt: 'Increasing the request buffer size can improve file sharing performance on high latency networks.'
type: post
id: 439
categories:
    - windows-2003_file-sharing
    - windows-nt4_file-sharing
    - windows-xp_file-sharing
    - windows-2000_file-sharing
tags:
    - microsoft-network
    - network-performance
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
  
 More info <a href="https://www.bing.com/search?q=KB%20123819%20Q123819" rel="nofollow" title="File Manager I/O Optimizations Slow other File Transfers [Q123819]">MS KB123819</a>  
 More info <a href="https://www.bing.com/search?q=KB%20151996%20Q151996" rel="nofollow" title="How to Improve Data Transfers over RAS, RRAS, or Slow Links [Q151996]">MS KB151996</a>  
 More info <a href="https://www.bing.com/search?q=KB%20152081%20Q152081" rel="nofollow" title="Use of Raw Data Transfer Mode Influenced by Application [Q152081]">MS KB152081</a>  
 More info <a href="https://www.bing.com/search?q=KB%20177266%20Q177266" rel="nofollow" title="Remote Directory Lists Are Slower Than Local Directory Listings [Q177266]">MS KB177266</a>  
 More info <a href="https://www.bing.com/search?q=KB%20223140%20Q223140" rel="nofollow" title="SMB Block Size Negotiation When Copying Files with Windows NT Explorer [Q223140]">MS KB223140</a>  
 More info <a href="https://www.bing.com/search?q=KB%20279282%20Q279282" rel="nofollow" title="Slow File Write from Windows 2000 to Windows NT 4.0 Server [Q279282]">MS KB279282</a>  
 More info <a href="https://www.bing.com/search?q=KB%20320829%20Q320829" rel="nofollow" title="HOW TO: Modify the Default SizReqBuf Value in Windows 2000 [Q320829]">MS KB320829</a>  