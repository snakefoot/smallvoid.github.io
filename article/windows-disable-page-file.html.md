---
title: 'Disable the page file to avoid using the slow HDD'
date: '2002-06-19T02:40:59+02:00'
status: publish
permalink: /article/windows-disable-page-file.html
author: Snakefoot
excerpt: 'Disabling the page file to prevent Windows from unloading memory to the hard disk.'
type: post
id: 234
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - free-disk-space
    - page-file
    - swap-file
post_format: []
tags:
    - 'swap-file,page-file,free-disk-space'
---
It is possible to disable the [page file](/article/windows-page-file.html), but it is not recommended.

- Disabling the page file will put a hard limit on the available virtual memory. Thus in extreme situations there will be no page file working as safety net.
- Disabling the page file will cause some applications to stop working, or make them behave odd.
- Even when the page file is disabled, then the operating system will still be paging when needing to load other files (EXE,DLL,etc.) into RAM.
- The [Performance Monitor](/article/winnt-performance-counters.html) (PerfMon) depends on the pagefile and requires minimum a 2 MB pagefile or else the counters will be missing for the following objects: Cache, Memory, Objects, Processor and System.
 
 There are circumstances where one might consider to disable the page file:
- If booting from a readonly media (Like a CD-ROM) where there is no available writeable media (Like an embedded device).
- If having an insane amount of memory compared to the most extreme memory usage expected. The paging algorithm is rather eager to page out memory, to have as much memory available for the 'awaiting' extreme situation, independent of how much memory there is available already. This hurts performance if using an application that is very memory intensive, but doesn't access all the memory constantly, thus generating many [page faults](/article/windows-pagefault.html). Though usually the problems with running without a pagefile will cancel out the gain.
 
 Note if finding out that you don't have enough memory to disable the pagefile then instead [Configure the pagefile for best performance](/article/windows-page-file.html).  
  
 More Info [MS KB316528](http://support.microsoft.com/kb/316528 ""Your System Has No Paging File, or the Paging File Is Too Small" Error Message After Windows XP Upgrade [Q316528]")  
 More Info [MS KB259184](http://support.microsoft.com/kb/259184 "How to Increase the Memory Capability of Your Computer [Q259184]")  
 More Info [MS KB196839](http://support.microsoft.com/kb/196839 "Windows Is Unstable After Disabling Virtual Memory [Q196839]")  
##### Disable the pagefile in Win9x

1. Start Button -&gt; Settings -&gt; Control Panel -&gt; System -&gt; Performance tab -&gt; Virtual Memory.
2. Select "Let me specify my own virtual memory settings".
3. Select "Disable virtual memory (Not recommended)".

##### Disable the pagefile in WinXP

 This can only be done if meeting the requirement of having minimum 512 Mbyte RAM installed.
1. Start Button -&gt; Control Panel -&gt; Performance and Maintenance -&gt; System -&gt; Advanced.
2. Under the "Performance" section press "Settings" button.
3. Under the "Virtual Memory" section press the "Change..." button.
4. Select "No paging file" for all drives.

##### Disable the pagefile in Vista

1. Start Button -&gt; Control Panel -&gt; System-applet -&gt; Advanced System Setting-task -&gt; Advanced-tab -&gt; Performance Settings...-button -&gt; Advanced-tab -&gt; Virtual Memory Change...-button (phew).
2. Untick "Automatically manage paging file size for all drives"
3. Select "No paging file" for all drives.