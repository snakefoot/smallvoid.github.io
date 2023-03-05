---
title: Superfetch
date: '2007-07-17T02:16:16+02:00'
status: publish
permalink: /article/winnt-services-sysmain.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Superfetch service.'
type: post
id: 703
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - disk-performance
    - file-cache
    - logical-prefetcher
post_format: []
tags:
    - 'logical-prefetcher,file-cache,disk-performance'
---
##### Description:

 Maintains and improves system performance over time.  
  
 Superfetch extends the [Prefetcher in Windows XP](/article/winnt-logical-prefetcher.html) by loading entire applications into memory beforehand. The original Prefetcher reacts to an application being started, and then pre-loads all the application modules before the application actually requests them. The new Superfetch loads the user's favorite applications into memory before the application is started by the user. This is also the reason why Vista seems like a memory hog even when doing "nothing".
- When starting the computer then Superfetch will automatically load the user's favorite applications into memory, so they are ready when the user actually starts them.
- When exiting a CPU and memory intensive application (like a game), then Superfetch will automatically load the user's favorite applications back into memory (If the favorite application are already running then they will be the first to be fetched back into memory from the [pagefile](/article/windows-page-file.html)). 
  - The same will happen when Windows own background tasks completes.
 
 Caching entire applications into memory can be rather memory intensive, which is why Microsoft also invented [Ready Boost](/article/winnt-services-emdmgmt.html). Though the general consensus is that when having more than 1 GByte RAM, then Ready Boost have little affect on the performance of Superfetch.  
  
 Superfetch is controlled by the following registry key:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager \\Memory Management \\PrefetchParameters\]  
>  EnableSuperFetch = 3 (Default = 3)  
>   
>  0 = Disable Superfetch (And the memory "hogging")  
>  1 = Enable prefetching when programs are launched  
>  2 = Enable boot prefetching  
>  3 = Enable prefetching of everything

 More Info [MSDN: Disable SuperFetch](http://msdn.microsoft.com/en-us/library/ff794658.aspx "Disable SuperFetch")  
 More Info [Technet: Description of SuperFetch](http://technet.microsoft.com/en-us/magazine/2007.03.vistakernel.aspx "Inside the Windows Vista Kernel: Part 2 (Mark Russinovich)")  
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (SysMain)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)