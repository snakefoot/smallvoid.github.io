---
title: 'Configure the timeout used when stopping / starting services'
date: '2002-01-05T18:50:57+01:00'
status: publish
permalink: /article/winnt-service-timeout.html
author: Snakefoot
excerpt: 'Change how long time to wait before a service is considered not responding and should be shut down.'
type: post
id: 381
category:
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - windows-services
post_format: []
tags:
    - windows-services
---
The Service Control Manager (SCM) is responsible for handling the startup and stopping of services. The SCM starts a service by launching the service-application, and then expects to receive a started-message from the service within a certain timeout.  
  
 Set this REG-DWORD key in the registry to specify the timeout in milliseconds:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control\]  
>  ServicesPipeTimeout = 30000  
>   
>  More Info [MS KB824344](http://support.microsoft.com/kb/824344 "How to debug Windows services [Q824344]")  
>  More Info [MS KB884495](http://support.microsoft.com/kb/884495 "Event ID 7000 appears in the System log and the ISA Server Storage service does not start when you start a computer that is running ISA Server 2004 [Q884495]")

 The SCM stops a service by sending a stop-message to the service and then expects to receive a stopped-message from the service within a certain timeout. Set this REG-SZ key in the registry to specify the timeout in milliseconds:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control\]  
>  WaitToKillServiceTimeout = "20000"  
>   
>  More Info [MS KB146092](http://support.microsoft.com/kb/146092 "How to Increase Shutdown Time for Services to Close Properly [Q146092]")  
>  More Info [MS KB839262](http://support.microsoft.com/kb/839262 "Services may stop abruptly when you shut down or restart a Windows Small Business Server 2003-based computer [Q839262]")

 Note if lowering the value too much it might cause improper shutdown of some services, which might lead to half-written / invalid / faulty data that will keep the service from starting properly again.  
  
 Note if having an UPS make sure it can supply enough power to support the shutdown of the machine properly, if increasing the value.  
  
 Related [Control Application Timeout](/article/windows-application-timeout.html)  