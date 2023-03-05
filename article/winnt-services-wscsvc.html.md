---
title: 'Security Center'
date: '2004-09-12T18:23:45+02:00'
status: publish
permalink: /article/winnt-services-wscsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Security Center service (WSCSVC).'
type: post
id: 592
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - network-access-protection
post_format: []
tags:
    - network-access-protection
---
##### Description:

 Monitors the health of the system by checking if proper firewall, antivirus, automatic-update policies are in place and working. More Info [MS KB883792](http://support.microsoft.com/kb/883792 "Frequently asked questions about Windows Security Center [Q883792]")  
  
 Note the Security Center provides different security warnings using balloon tips, and they can be turned off through the Security Center interface. But one can also do it by setting these DWORD values:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Security Center\]  
>  AntiVirusOverride = 1 (0 = Antivirus monitoring)  
>  AntiSpywareOverride = 1 (0 = Anti Spyware monitoring  
>  FirewallOverride = 1 (0 = Firewall monitoring)  
>   
>  Related [Disable Balloon Tips](/article/winnt-balloon-tip.html#SECURITY_CENTER)

 Note Security Center also functions as Windows Security Health Validator (WSHA) used by the [Network Access Protection Agent](/article/winnt-services-napagent.html). It can provide the following health information:
- Firewall is enabled
- Antivirus is enabled and up-to-date
- Antispyware is enabled and up-to-date
- Automatic Updates is enabled
- Security updates are up-to-date
 
 Note if the [WMI Repository is corrupted](/article/winnt-wmi-config.html), then the Security Center might report problems that aren't true or other outdated / misleading information.  
##### Recommended State:

- Disabled.

##### Default State:

- Win8/Win7/Vista: Automatic (Delayed Start).
- WinXP SP2: Automatic.

##### Process Name:

- Win8/Win7/Vista: [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (wscsvc)
- WinXP SP2: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (wscsvc)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Windows Management Instrumentation (WMI)](/article/winnt-services-winmgmt.html)