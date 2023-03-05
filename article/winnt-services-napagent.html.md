---
title: 'Network Access Protection Agent'
date: '2007-07-17T02:14:42+02:00'
status: publish
permalink: /article/winnt-services-napagent.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Network Access Protection Agent service (also called Quarantine Agent).'
type: post
id: 683
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

 Enables Network Access Protection (NAP) functionality on client computers.  
  
 NAP makes it possible to specify health policies, that ensures client computers doesn't get access to the trusted network unless they satisfy the wanted security levels. This can be used for laptop computers that might have been connected to insecure hotspots or similar before connecting to the corporate network.  
  
 Note depending on which System Health Validators (SHVs) are used in the health policies, the client System Health Agents (SHAs) may need different operating system components. For example [Security Center](/article/winnt-services-wscsvc.html) must be enabled to use Microsoft's Windows Security Health Validator (WSHV).  
  
 Note Windows Vista/2008 includes a NAP Client Configuration MMC (napclcfg.msc), but WinXP SP3 only has the netsh tool available:
> netsh nap client set enforcement ID = &lt;id&gt; Admin = "Enable"  
>   
>  Where &lt;id&gt; can be:
> 
> - DHCP = 79617
> - RAS = 79618
> - IPSec = 79619
> - TS Gateway = 79621
> - EAP = 79623

 More Info [Cable Guy – Network Access Protection Platform Overview](http://www.microsoft.com/technet/community/columns/cableguy/cg0705.mspx)  
 More Info [Cable Guy – Troubleshooting NAP Enforcement](http://technet.microsoft.com/en-us/magazine/cc434701.aspx "The Cable Guy  Troubleshooting NAP Enforcement (April 2008)")  
 More Info [MS Technet - Network Access Protection (NAP)](http://technet.microsoft.com/en-us/network/bb545879.aspx)  
 More Info [MSDN - NAP Client Architecture](http://msdn2.microsoft.com/en-us/library/aa369712.aspx)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win8/Win7/Vista: [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (napagent)
- WinXP SP3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (napagent)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)