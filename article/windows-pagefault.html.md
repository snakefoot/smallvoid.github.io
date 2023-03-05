---
title: 'Description of soft and hard page faults'
date: '2015-11-17T01:04:23+01:00'
status: publish
permalink: /article/windows-pagefault.html
author: Snakefoot
excerpt: 'Description of how Windows optimizes the virtual memory to minimize the need for hard pagefaults.'
type: post
id: 2588
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - memory-manager
    - page-fault
    - page-file
    - virtual-memory
post_format: []
---
##### Windows Memory

 Applications needs memory and will ask Windows to provide this. Windows can get memory from the quick RAM or from the slow disk. When there is not enough quick RAM to run a new application, then Windows will attempt to free RAM by paging other running applications to the [pagefile on the slow disk](/article/windows-page-file.html).  
  
 Windows constantly trims the [working memory](/article/winnt-memory-decommit.html) of the running applications, and puts less frequently used memory-pages on a standby-list. Slowly the memory-pages in the standby-list are paged out to the disk, but the memory pages are still kept in RAM. This allows Windows to quickly give the RAM to a new application when needed, but also allows the running application to reference the memory-page without going to disk.  
  
 When application has been standby for a long time, then it will take a long time to activate the application again. The application will slowly load itself into memory, because each memory-page access will give a pagefault:
- **Hard Page Fault** - The application memory-page has been paged to disk, and now it has to be loaded from disk. This is a blocking operation and will hurt application performance.
- **Soft Page Fault** - The application memory-page resides in the standby-list, and can be quickly loaded back into the application working set. 
  - Soft Page faults also happens when the application allocates new memory-pages, by taking them from the free-list / standby-list.
 
 The Pagefaults Performance Counters (Or PF-Delta in Task Manager) includes both hard- and soft-pagefaults. If the PF-Delta is high for a running application, then it usually means it is frequently throwing away memory just allocated. The application developer should consider reusing the same memory objects once created.  
  
 More Info [The Basics of Page Faults](http://blogs.technet.com/b/askperf/archive/2008/06/10/the-basics-of-page-faults.aspx)
 
##### Windows XP Prefetch

 Windows can monitor what files an application uses at startup, and next time the application starts then automatically load these files into the [file cache](/article/winnt-system-cache.html). Application startup will then be faster. [Logical Prefetcher](/article/winnt-logical-prefetcher.html)
 
##### Windows Vista Superfetch

 Windows can monitor what application you frequently use, and ensure the file cache has preloaded the application files. Application startup will then be faster. More memory is then used for [disk caching](/article/winnt-system-cache.html), unless a running application needs it. Windows will also prioritize that frequently used applications are the last ones to be paged to disk. [Superfetch](/article/winnt-services-sysmain.html)
 
##### Windows 8 Swap

 Windows can optimize the paging of mobile application that supports suspend-/resume-state. Instead of writing separate memory pages of only 4 KByte, then will pre-allocate memory in the pagefile that fits the entire application, so it can be written to pagefile in one big disk write. This will also make it faster for the application to be paged back from the disk.
 
##### Windows 10 Compressed Store

 Windows can optimize the usage of the quick RAM, by paging the application memory to a compression store instead of directly to the paging file. The compression store resides in memory of the standard system-process. Special store has been made for mobile applications that supports suspend-/resume-state, that allows them to swap into compressed state, and if needed also swap the (now smaller) compressed memory to the pagefile.  
  
 When trimming the working memory of an application, then instead of writing to disk, then they are kept in the compression store. Unless memory pressure requires them to be written to disk. This will minimize disk usage and avoids the disk from being worn out.