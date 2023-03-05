---
title: 'Multimedia Class Scheduler'
date: '2007-07-17T02:14:32+02:00'
status: publish
permalink: /article/winnt-services-mmcss.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Multimedia Class Scheduler service.'
type: post
id: 681
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - process-priority
    - process-scheduler
    - windows-media-player
post_format: []
tags:
    - 'process-priority,process-scheduler,windows-media-player'
---
##### Description:

 Enables relative prioritization of work based on system-wide task priorities. This is intended mainly for multimedia applications. If this service is stopped, individual tasks resort to their default priority.  
  
 Multimedia Class Scheduler service (MMCSS) gives multimedia applications higher priority. This ensures that music and video playback will not be disturbed by other background services like antivirus and content indexing (or network file transfers). More Info [Technet Magazine February 2007 - Inside Vista Kernel](http://www.microsoft.com/technet/technetmag/issues/2007/02/VistaKernel/#S3), [MSDN - Multimedia Class Scheduler Service](http://msdn2.microsoft.com/en-us/library/ms684247.aspx).  
  
 Note if wanting to disable this this service without loosing sound, then remove MMCSS from the DependOnService-list for [Windows Audio](/article/winnt-services-audiosrv.html) before disabling it:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Audiosrv\]  
>  DependOnService = "..."

 Note another way to disable this service is to change the limit CPU resources that should be guaranteed for low-priority tasks. > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Multimedia \\SystemProfile\]  
>  SystemResponsiveness = 20 (10-100%, 100 disables MMCSS)  
>   
>  Vista Default = 20%, W2K8 Default = 100%.

##### Recommended state:

- Automatic if you like sound

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (MMCSS)

##### Supports:

- [Windows Audio](/article/winnt-services-audiosrv.html)

##### Depends:

- none