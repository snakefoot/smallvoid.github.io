---
title: 'Install an application as a Windows service'
date: '2003-01-10T17:33:45+01:00'
status: publish
permalink: /article/winnt-services-srvany.html
author: Snakefoot
excerpt: 'Running an application as a service allows the application to run without a user needing to login.'
type: post
id: 511
category:
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag:
    - windows-services
post_format: []
tags:
    - windows-services
---
[Srvany.exe](ftp://ftp.microsoft.com/bussys/winnt/winnt-public/reskit/nt40/i386/srvany_x86.exe) ([Download mirror](http://smallvoid.orgfree.com/?file=srvany.zip)) allows one to install a standard application as service. The Srvany acts as a wrapper around the program and handles the service events, so when starting the service it will run the application. One uses the Instsrv.exe to register the Srvany with a service name, and then uses the registry to attach the application which should be started through Srvany.  
> Instsrv.exe MyService C:\\Srvany.exe

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\MyService \\Parameters\]  
>  Application = "C:\\MyApp.exe"

 Note one can control the new service from the command line using SC.EXE or NET.EXE.  
  
 Note [FireDaemon](http://www.firedaemon.com/) is similar to Srvany with more bells and whistles, but it costs money.  
  
 Note instead of running an application as a service, then one can also consider using a scheduled task to start the application when computer starts or when a user performs logon. See [Task Scheduler](/article/winnt-services-schedule.html).  
  
 More Info [MS KB137890](http://support.microsoft.com/kb/137890 "HOWTO: Create a User-Defined Service [Q137890]")  
 More Info [MS KB166819](http://support.microsoft.com/kb/166819 "Using Sc.exe and Netsvc.exe to Control Services Remotely [Q166819]")  
 More Info [MS KB251192](http://support.microsoft.com/kb/251192 "How to Create a Windows Service Using Sc.exe [Q251192]")  