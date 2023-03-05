---
title: 'Task Scheduler'
date: '2000-06-06T16:26:04+02:00'
status: publish
permalink: /article/winnt-services-schedule.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Task Scheduler service.'
type: post
id: 590
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - bootvis
    - logical-prefetcher
    - scheduled-task
    - system-restore
    - task-scheduler
post_format: []
tags:
    - 'logical-prefetcher,bootvis,system-restore,task-scheduler,scheduled-task'
---
##### Description:

 Makes it possible to schedule a command or program to execute at a specified time &amp; date.  
 This service is also referred to as the AT service, and is required for the AT command. The Task Scheduler listens on a dynamic TCP port starting from 1025, depending whether other applications tries to acquire a dynamic TCP port then it might get port no. like 1026 or higher.  
  
 Note that with IE5 a new task scheduler came which allows one to use GUI interface to configure tasks. Though these tasks cannot be seen with AT. More Info [MS KB220149](http://support.microsoft.com/kb/220149 "AT Tasks Cannot Be Viewed Using the Task Scheduler Tool [Q220149]")  
  
 Note in WinXP the AT command has been replaced with Schtasks. One can modify the [Schtasks.exe](/article/win2k-task-scheduler-schtasks.html) so it works with Win2k.  
  
 Note in WinXP a new policy has been introduced, which prevents running scheduled tasks using an account which has no password. More Info [MS KB311119](http://support.microsoft.com/kb/311119 "Task Scheduler Does Not Run Tasks When "Run As" User Account Has No Password [Q311119]")  
  
 Note in Win2k the Task Scheduler might fail to schedule tasks with the following error if [Protected Storage](/article/winnt-services-protectedstorage.html) have become corrupt:
> *The new task has been created, but may not run because the account information could not be set. The specific error is: 0x80090016: Keyset does not exist.  
>  0x8009000f: Object already exists.*

 Note in Vista the Task Scheduler now includes several default tasks, which are triggered by things like windows-startup, user-login, eventlog-events, time-event, etc. More Info [MS KB939039](http://support.microsoft.com/kb/939039)  
  
 Related [Configure the Task Scheduler Log](/article/windows-task-scheduler-log.html)  
  
 More Info [MS KB124859](http://support.microsoft.com/kb/124859 "Allowing Non-Administrators to Use the AT command [Q124859]")  
 More Info [MS KB138340](http://support.microsoft.com/kb/138340 "Trouble Quitting Program Started with AT.EXE Scheduler [Q138340]")  
 More Info [MS KB142040](http://support.microsoft.com/kb/142040 "Troubleshooting AT Command Using /k Switch [Q142040]")  
 More Info [MS KB158825](http://support.microsoft.com/kb/158825 "System and User Account Difference with AT Command [Q158825]")  
 More Info [MS KB171773](http://support.microsoft.com/kb/171773 "How to Eliminate a Process That Is Not Responding Without Restarting the Computer [Q171773]")  
 More Info [MS KB178706](http://support.microsoft.com/kb/178706 "How to Schedule a Program Using Task Scheduler [Q178706]") (How to create scheduled task in Win98)  
 More Info [MS KB304288](http://support.microsoft.com/kb/304288 "A Task That Is Scheduled with the AT Command May Stop After 72 Hours [Q304288]")  
 More Info [MS KB308569](http://support.microsoft.com/kb/308569 "HOW TO: Schedule Tasks in Windows XP [Q308569]") (How to create scheduled task in WinXP)  
 More Info [MS KB313565](http://support.microsoft.com/kb/313565 "HOW TO: Use the AT Command to Schedule Tasks [Q313565]")  
 More Info [MS KB814596](http://support.microsoft.com/kb/814596 "HOW TO: Use Schtasks.exe to Schedule Tasks in Windows Server 2003 [Q814596]")  
 More Info [MS Technet - Scheduled Tasks in Windows Vista](http://technet.microsoft.com/en-us/appcompat/aa906020.aspx "Windows Vista Task Scheduler")   
##### Recommended State:

- Automatic, if using WinXP/Vista and wants [prefetching](/article/winnt-logical-prefetcher.html), [bootvis](/article/winxp-bootvis.html) and [System Restore](/article/winnt-services-srservice.html) to work properly.
- Disabled, if programs are not needed to be scheduled to start at a specific time.

##### Default State:

- Automatic

##### Process Name:

- WinNT4: Atsvc.exe (Schedule)
- Win2k/WinNT4 + IE5: MSTask.exe (Schedule)
- WinXP/Win2k3/Vista: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Schedule)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Windows Event Log](/article/winnt-services-eventlog.html) (Vista+)