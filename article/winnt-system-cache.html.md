---
title: 'Configure the file system cache in Windows NT'
date: '2000-01-01T19:18:24+01:00'
status: publish
permalink: /article/winnt-system-cache.html
author: Snakefoot
excerpt: 'How to configure memory size of the file cache for faster file operations.'
type: post
id: 265
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - disk-performance
    - file-cache
    - file-system
post_format: []
tags:
    - 'file-system,file-cache,disk-performance'
---
Windows has a file caching mechanism which is tightly integrated with the memory manager. It helps disk performance by keeping the most recent files in memory, whether is is EXE or DLL files loaded by the memory manager or data files loaded by the running applications.  
  
 The filesystem cache can work in two different modes:

- The default mode is that the filesystem cache only grows to a certain limit (8 MByte).
- The other mode is that the file system cache can grow until it has taken all memory (Up to 1 GByte depending on available memory).
 
 One should not change from the default mode on standard workstations as a single application can trigger the file system cache to take all available RAM (Ex. by copying a large file), and the memory of other applications will be [paged to disk](/article/windows-page-file.html) (Even more I/O)  
  
 To allow the file system cache to make use of "all" available memory: - **WinNT4**: Open Control Panel -&gt; Network -&gt; Change properties for "Server" service to use "Maximize Throughput for File Sharing" (Will also change [Server service memory usage](/article/winnt-server-config.html)).
- **Win2k**: Open Control Panel -&gt; Network and Dial-up Connections -&gt; Right-click Local Area Connection and select Properties -&gt; Press Properties for service "File and Print Sharing for Microsoft Networks" to set "Maximize Data Throughput for File Sharing" (Will also change [Server service memory usage](/article/winnt-server-config.html))..
- **WinXP/Win2k3**: Open Control Panel -&gt; System-Applet -&gt; Advanced-Tab -&gt; Performance-Settings-Button -&gt; Advanced-Tab and select "System Cache"-Option.
- **Registry**:
  > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Session Manager \\Memory Management\]  
  >  LargeSystemCache=1 (Default Srv. = 1, Default Prof. = 0)
 
 Note if wanting better control than just size Large and Small then try one of these utilities: - [Microsoft Windows Dynamic Cache Service](http://www.microsoft.com/downloads/details.aspx?FamilyID=e24ade0a-5efe-43c8-b9c3-5d0ecb2f39af) - Microsoft have recognized that 64bit versions of Windows has problems controlling the size if the working set for the file system cache ([Up to 1 TB](http://support.microsoft.com/kb/294418 "Comparison of 32-bit and 64-bit memory architecture for 64-bit editions of Windows XP and Windows Server 2003")). This service can control the size of the file system cache according to workload, which can be useful if not using Windows 7 that tries to fix this issue. More Info [NTDebugging](http://blogs.msdn.com/ntdebugging/archive/2009/02/06/microsoft-windows-dynamic-cache-service.aspx)
- [SetCache](http://blogs.msdn.com/ntdebugging/archive/2007/11/27/too-much-cache.aspx "Too Much Cache?") - Sets a permanent upper limit for the file cache using the [SetSystemFileCacheSize](http://msdn2.microsoft.com/en-us/library/aa965240.aspx) API (Win2k3/Win2k8/Vista only). Use a trigger to activate this tool to set file cache limits at startup.
- [SysInternals CacheSet](http://www.microsoft.com/technet/sysinternals/FileAndDisk/CacheSet.mspx) - It can only reset the cache to a certain size from where it can grow or shrink again.
- [Uwe Sieber - NtCacheSet](http://www.uwe-sieber.de/ntcacheset_e.html) - Periodically resets the cache working set, just like CacheSet but does it with a specified interval.
- [Uwe Sieber - SetSystemFileCacheSize](http://www.uwe-sieber.de/ntcacheset_e.html) - Sets a permanent upper limit for the file cache using the [SetSystemFileCacheSize](http://msdn2.microsoft.com/en-us/library/aa965240.aspx) API (Win2k3/Win2k8/Vista only). Use a trigger to activate this tool to set file cache limits at startup.
 
 Note Win2k3 SP2 includes a new registry setting that controls how much physical memory, the file cache can use for data that has to be written to disk. By default the file cache can occupy half of the physical memory, so when copying a large file (&gt;500 MByte) then it will read the file into the cache until it reaches the limit. When it reaches the limit it throttles the file reading until it has written the contents of the cache to disk. This can cause the memory manager to hang, along with all applications, so one should consider to limit the size of the write cache:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\SessionManager \\MemoryManagement\]  
>  SystemCacheDirtyPageThreshold = 100 (MByte; Default = 0; 0 = Half of physical memory)  
>   
>  More Info [MS KB920739](http://support.microsoft.com/kb/920739 "You may experience a decrease in overall system performance when you are copying files that are larger than approximately 500 MB in Windows Server 2003 SP1") (Doesn't limit the size of the read cache)

 Note the LargeSystemCache is allocated from [kernel memory area](/article/winnt-kernel-memory.html), which is shared with the pagedpoolsize and systempages. So when limiting these from using max size, then it will allow the filesystem cache to reach its max size of 960 MByte (WinNT4 512 MByte), else it will be limited to 512 MByte.  
  
 Note not all applications will benefit from a large system cache. Many disk intensive applications (Like database systems) includes their own cache manager, and doesn't make use of the operating system controlled file cache. For MS SQL and Exhange the optimal value is to disable the large system cache.  
  
 Note enabling the large system cache can give stability issues, because it will configure the kernel area to allocate max memory for the file cache, while sacrificing the size of memory pools and number of page table entries. If using Unified Memory Architecture (UMA)-based video hardware or an Accelerated Graphics Port (AGP), then it will require page table entries to address the video memory. ATI [recommends](http://support.ati.com/ics/support/default.asp?deptID=894&task=knowledge&searchOption=id&questionID=986 "Data corruption may occur if the Large System Cache feature is enabled in Windows XP (Topic 737-986)") one doesn't enable large system cache to avoid data corruption. More Info [MS KB895932](http://support.microsoft.com/kb/895932 "Things to consider before you enable System cache mode in Windows XP [Q895932]")  
  
 More Info [MS Technet - File Cache Performance and Tuning](http://www.microsoft.com/technet/prodtechnol/windows2000serv/maintain/optimize/wperfch7.mspx) (Good read)  
 More Info [MS Technet - Optimizing your memory configuration](http://www.microsoft.com/technet/prodtechnol/windows2000serv/reskit/core/fnec_evl_fhcj.mspx "Evaluating Memory and Cache Usage")  
 More Info [MS KB232271](http://support.microsoft.com/kb/232271 "How to Optimize Windows NT Server Using the Registry [Q232271]")  
 More Info [MS KB228766](http://support.microsoft.com/kb/228766 "How to Change the Server Service Properties [Q228766]")  
 More Info [MS KB837331](http://support.microsoft.com/kb/837331 "About Cache Manager in Windows Server 2003 [Q837331]")  
  
 Credits [ArsTechnica.com](http://www.arstechnica.com/)