---
title: 'Increase the priority of the foreground application'
date: '2001-01-31T20:31:14+01:00'
status: publish
permalink: /article/win9x-priority.html
author: Snakefoot
excerpt: 'How to give the foreground application higher priority, so it will not be disturbed by background processes.'
type: post
id: 95
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - process-priority
    - process-scheduler
post_format: []
tags:
    - 'process-priority,process-scheduler'
---
Windows 9x gives by default all applications equal priority. One can configure Windows to give the application in the foreground higher priority, so it will not be disturbed by background applications.  
  
 Add/Update these DWORD values in the registry:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\BIOS\]  
>  CPUPriority = 1 (0=Realtime, 1=Foreground Max, 2=Foreground Med, 3=Equal) (Default=3)  
>  FastDRAM = 1  
>  PCIconcur = 1  
>  AGPconcur = 1 (For those with AGP display adapter)

 Note that computers, which are using ACPI and not having a "Plug and Play BIOS" in the "Device Manager" under "System Devices", should not use these settings.  
  
 Credits [www.mdgx.com](http://www.mdgx.com/)