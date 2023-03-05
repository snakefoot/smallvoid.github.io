---
title: 'Configure memory manager to minimize memory fragmentation'
date: '2006-02-28T01:51:47+01:00'
status: publish
permalink: /article/winnt-memory-decommit.html
author: Snakefoot
excerpt: 'Memory manager should only mark a continuous memory block as free when the block has reached a certain size.'
type: post
id: 379
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - decommit
    - memory-manager
    - private-bytes
    - virtual-bytes
    - virtual-memory
post_format: []
tags:
    - 'memory-manager,decommit,virtual-bytes,private-bytes,virtual-memory'
---
All applications uses memory, and while running they can make different requests to the memory manager ([VirtualAlloc](http://msdn2.microsoft.com/en-us/library/aa366887.aspx) / [VirtualFree](http://msdn2.microsoft.com/en-us/library/aa366892.aspx)):

- **Commit** memory, when the application wants to allocates more memory for its own use
- **Reserve** memory, when the application wants to reserve a contiguous block of memory without allocating physical memory
- **Decommit** memory. when the application wants to change committed memory to reserved memory (Release physical memory)
- **Free** memory, when the application wants to release committed/reserved memory so other processes can use the memory address space instead
 
 By default when an application decommits a range of memory blocks, then the memory manager will change the memory range to reserved (no matter how small a range). If the application commits / decommits often, then there is a high chance that it will fragment the reserved memory range, and make it difficult for the application to commit a large contiguous memory block without increasing the reserved memory range.  
  
 To monitor if the virtual memory has become fragmented, one can use [Perfmon](/article/winnt-services-sysmonlog.html) and Add Counters... from the [Process](http://msdn.microsoft.com/library/en-us/wmisdk/wmi/win32_perfformatteddata_perfproc_process.asp) Performance Object. - **Private Bytes** - The total amount of memory (RAM + pagefile) requested by the process.
- **Working Set** - Total physical memory (RAM) used by the process
- **Virtual Bytes** - The virtual address space occupied by the process
 
 If Virtual Bytes grows much larger than Private Bytes over time, then it can be an indication that memory fragmentation is happening. If Virtual Bytes is much larger than Private Bytes at application start, then it can indicate that the application just reserves virtual memory at startup. If Virtual Bytes is close to Peak Working Set Size, then it can indicate that the process at a moment in time required extra memory, and then released it again but created some innocent memory fragmentation. If Private Bytes (VM Size in Windows Task Manger) grows continuously, then it can indicate that the application has a memory leak.  
> The Task Manager in Windows 7/2008 has the following important columns:
> 
> - Working Set (Memory) - Physical memory used by the process, includes memory shared with other processes (DLL's etc.)
> - Memory (Private Working Set) - Physical memory used by process alone
> - Commit Size - Virtual memory used by the proces, includes RAM and pagefile (Private Bytes)

 Microsoft introduced a new heap implementation called low fragmentation heap (LFH) with Windows XP / 2003 (Back ported to Win2k SP4). If developing an application that is very memory intensive, then one can activate the LFH [HeapSetInformation()](http://msdn.microsoft.com/en-us/library/aa366705.aspx), instead of creating a home built memory allocator. The LFH uses fixed sized buckets so small and large allocations are not mixed together, but at the cost of higher memory usage because the buckets introduces slack. More Info [MSDN - Low-fragmentation Heap](http://msdn.microsoft.com/en-us/library/aa366750.aspx) [MSDN - Heap: Pleasures and Pains](http://msdn.microsoft.com/en-us/library/ms810466.aspx)  
  
 It is possible to change the behavior of the memory manager, so instead of performing the decommit right away, then it will only decommit when it there is a contiguous memory block of a certain size to decommit. This change in behavior will lower the chance of memory fragmentation, but will also generate a memory overhead, and should only be considered if having more than 1 GByte RAM, and having problems with virtual memory fragmentation.
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager\]  
>  HeapDecommitFreeBlockThreshold = 262144 (Default = 0)  
>   
>  More Info [MS KB315407](http://support.microsoft.com/kb/315407 "The "HeapDecommitFreeBlockThreshold" registry key [Q315407]")

 More Info [MSDN](http://msdn.microsoft.com/en-us/library/ms810627.aspx) (Managing Virtual Memory in Win32)  
 More Info [MS KB325044](http://support.microsoft.com/kb/325044 "How to troubleshoot virtual memory fragmentation in Exchange Server 2003 and Exchange 2000 Server [Q325044]")  
 More Info [MS KB815372](http://support.microsoft.com/kb/815372 "How to optimize memory usage in Exchange Server 2003 [Q815372]")  