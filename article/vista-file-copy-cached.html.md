---
title: 'Change the Vista file copy to perform like in earlier versions'
date: '2007-09-06T00:55:39+02:00'
status: publish
permalink: /article/vista-file-copy-cached.html
author: Snakefoot
excerpt: 'Configure the file copying method to use cached I/O requests instead of non-cached.'
type: post
id: 742
category:
    - 'Tweak Performance'
tag:
    - disk-performance
    - file-cache
    - file-copy
    - hard-disk-drive
post_format: []
tags:
    - 'file-cache,hard-disk-drive,disk-performance,file-copy'
---
Windows Vista changes the behavior of the file copying operations, by using non-cached I/O requests (Before it was cached). This means that it will not check if the file in the [system file cache](/article/winnt-system-cache.html) before starting the file copy, and the file will not enter the cache during the direct file copy from source to destination.

- **Update with Vista SP1** - The default file copy routine has been reverted back to perform cached file copying by default. Except when a remote file is read or written, then it tells the client-side remote file system driver (Rdbss.sys) not to perform caching, so only the local read or write operation is cached in memory. More Info [Mark Russinovich](http://blogs.technet.com/markrussinovich/archive/2008/02/04/2826167.aspx "Inside Vista SP1 File Copy Improvements")
 
 Normally when copying large files using cached I/O request, then it can ruin the file cache by either flushing out all other cached files, or make it grow so large that it depletes the physical memory or unloads memory to the [pagefile](/article/windows-page-file.html). Therefore it is a good idea to use non-cached I/O when doing file copying.  
  
 But apparently the I/O rutines in the system file cache manager are so fast that even if it ruins the file cache, then the cached file copying is quicker. This is probably because the file cache works like a large read ahead buffer. When doing a file copy on the same disk, then it doesn't have to constantly move the hard disk head back and forth between source and destination. Another reason why cached file copying feels quicker is that when the cache manager has read the entire file into memory, then the file copy dialog is closed before it has finished writing to the destination file.  
  
 Configure this DWORD registry value to use cached I/O requests when doing file copy:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Policies \\Microsoft \\Windows \\System\]  
>  CopyFileBufferedSynchronousIo = 1 (Default = 0)  
>   
>  More Info [MS KB941673](http://support.microsoft.com/kb/941673 "After you add the CopyFileBufferedSynchronousIo registry entry in Windows Vista, a file copies only slightly more quickly when you use Windows Explorer to copy the file to another computer") (Hotfix is required)

 Note Microsoft have identified several performance issues in Windows Vista, and created several patches that address some of these issues. [MS KB938194](http://support.microsoft.com/kb/938194 "An update is available that improves the compatibility and reliability of Windows Vista"), [MS KB938979](http://support.microsoft.com/kb/938979 "An update is available that improves the performance and reliability of Windows Vista"), [MS KB941649](http://support.microsoft.com/kb/941649 "An update is available that improves the compatibility, reliability, and stability of Windows Vista"), [MS KB941600](http://support.microsoft.com/kb/941600 "Cumulative update rollup for USB core components in Windows Vista"), [MS KB943899](http://support.microsoft.com/kb/943899 "An update that improves the performance, responsiveness, and reliability of Windows Vista is available") (Will over time be available on Windows Update, and will be part of Vista SP1).  
  
 Related [Slow file copy caused by automatic tuning of TCP/IP RWIN](/article/vista-tcpip-auto-rwin.html)  
  
 Credits [blog.tiensivu.com](http://blog.tiensivu.com/aaron/)