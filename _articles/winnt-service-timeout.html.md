---
title: 'Configure the timeout used when stopping / starting services'
date: '2002-01-05T18:50:57+01:00'
permalink: /article/winnt-service-timeout.html
author: Snakefoot
excerpt: 'Change how long time to wait before a service is considered not responding and should be shut down.'
type: post
id: 381
categories:
    - windows-2003_tips
    - windows-nt4_tips
    - windows-xp_tips
    - windows-2000_tips
tags:
    - windows-services
---
The Service Control Manager (SCM) is responsible for handling the startup and stopping of services. The SCM starts a service by launching the service-application, and then expects to receive a started-message from the service within a certain timeout.  
  
 Set this REG-DWORD key in the registry to specify the timeout in milliseconds:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control\]  
>  ServicesPipeTimeout = 30000  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20824344%20Q824344" rel="nofollow" title="How to debug Windows services [Q824344]">MS KB824344</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20884495%20Q884495" rel="nofollow" title="Event ID 7000 appears in the System log and the ISA Server Storage service does not start when you start a computer that is running ISA Server 2004 [Q884495]">MS KB884495</a>

 The SCM stops a service by sending a stop-message to the service and then expects to receive a stopped-message from the service within a certain timeout. Set this REG-SZ key in the registry to specify the timeout in milliseconds:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control\]  
>  WaitToKillServiceTimeout = "20000"  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20146092%20Q146092" rel="nofollow" title="How to Increase Shutdown Time for Services to Close Properly [Q146092]">MS KB146092</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20839262%20Q839262" rel="nofollow" title="Services may stop abruptly when you shut down or restart a Windows Small Business Server 2003-based computer [Q839262]">MS KB839262</a>

 Note if lowering the value too much it might cause improper shutdown of some services, which might lead to half-written / invalid / faulty data that will keep the service from starting properly again.  
  
 Note if having an UPS make sure it can supply enough power to support the shutdown of the machine properly, if increasing the value.  
  
 Related [Control Application Timeout](/article/windows-application-timeout.html)  