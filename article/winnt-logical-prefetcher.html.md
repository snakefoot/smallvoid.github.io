---
title: 'Configure the logical prefetcher for faster application start'
date: '2001-12-29T18:58:31+01:00'
status: publish
permalink: /article/winnt-logical-prefetcher.html
author: Snakefoot
excerpt: 'Microsoft Windows can speed up the launch of application by prefetching the data the application usually request at startup.'
type: post
id: 366
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - defrag
    - logical-prefetcher
    - task-scheduler
post_format: []
tags:
    - 'logical-prefetcher,defrag,task-scheduler'
---
Windows XP includes a new enhancement to the memory management. It is called the Logical Prefetcher and it can make boot time and application start time faster. The Logical Prefetcher records disk usage in certain scenarios (Bootup and Application start), and when the same scenario reappear, it loads all the data needed for that scenario from disk to memory, before the data is requested.  
  
 The behavior of the Prefetcher is controlled with this DWORD registry key:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager\\ Memory Management \\PrefetchParameters\]  
>  EnablePrefetcher = 3 (Disabled = 0, Application = 1, BootUp = 2, Application AND BootUp = 3)  
>   
>  Note Windows Home and Professional edition will by default enable the prefetcher for both Application and BootUp. Windows Server edition will by default only enable the prefetcher to optimize bootup.  
>   
>  Note if using other values like 5 or 6 then it will either disable the prefetcher or only activate one of the prefetching types.  
>   
>  Note the Prefetcher is a service that runs in background and monitors disc and memory usage, and this monitoring requires CPU and RAM. If having less than 800 Mhz CPU and 512 MByte RAM, then one should consider only to enable the BootUp prefetcher.  
>   
>  More Info [MS KB307498](http://support.microsoft.com/kb/307498 "How to Disable the Prefetcher Component in Windows XP [Q307498]")

 The [Task Scheduler](/article/winnt-services-schedule.html) notifies when a process has started, causing the prefectcher to start monitoring the first 10 secs of the process start, and then saves the recorded disk activity caused by the process in a \*.pf file in the Prefetch-directory:
> C:\\WinNT\\Prefetch or C:\\Windows\\Prefetch  
>   
>  Note if deleting the contents of the prefetch directory, then it will loose all history of how to optimize the launch of application and will ruin the concept the prefetcher.  
>   
>  Note it can be a good idea to clear the prefetch directory when having applied a service pack for Windows or other applications, so the optimizer will quickly adapt to the updated files. Also if using AntiVira software, then this directory should be excluded to lower disc activity.

 The Prefetch-directory also contains a file Layout.ini, which is generated from the saved scenarios. The Layout.ini is used when doing a full defragmentation where frequently used files are aligned for faster loading. The Layout.ini is by default generated automatically, but one can also force the generation with command (Will run for 1-10 min):
 > rundll32.exe advapi32.dll,ProcessIdleTasks

 Note one can do a quick/partial defrag according to the Layout.ini, and only optimize the boot- and application- files for faster startup using [Defrag.exe](/article/winnt-defrag-switches.html):
 > defrag c: -b

 Note the generation of the Layout.ini and the partial defragmentation (dfrgntfs.exe) is automatically started when the computer is idle (or within every 3rd day). One can configure this automatic defragmentation of the computer with these registry keys:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\OptimalLayout\]  
>  EnableAutoLayout = 0 (Optimize Programs=1, Disabled = 0, Default = 1)  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Dfrg \\BootOptimizeFunction\]  
>  Enable = "Y" (Optimize Booting="Y", Disabled = "N", Default = "Y")  
>   
>  Note other processes also starts when the computer is registered as idle, so if having problems using the computer after it has been idle, then it is most likely caused by the [Indexing Service](/article/winnt-services-cisvc.html).  
>   
>  More Info [MS KB313300](http://support.microsoft.com/kb/313300 "Hard Disks Do Not Turn Off After Your Computer Has Been Idle [Q313300]")

 More Info [MS WHDC - Benchmarking on Windows XP](http://www.microsoft.com/whdc/system/sysperf/benchmark.mspx "Benchmarking on Windows XP")  
 More Info [MS WHDC - Kernel Enhancements for Windows XP](http://www.microsoft.com/whdc/driver/kernel/XP_kernel.mspx "Kernel Enhancements for Windows XP")  
 More Info [MS MSDN - Windows XP Kernel Improvements](http://msdn.microsoft.com/en-us/magazine/cc302206.aspx "Windows XP: Kernel Improvements Create a More Robust, Powerful, and Scalable OS")  
  
 Credits [TweakXP.com](http://www.tweakxp.com/)