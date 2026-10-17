---
title: 'Distributed Transaction Coordinator'
date: '2000-07-23T01:17:01+02:00'
permalink: /article/winnt-services-msdtc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Distributed Transaction Coordinator service.'
type: post
id: 540
categories:
    - windows-2000_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
    - windows-8-win8_services-guide
tags: []
---
##### Description:

 Distributed Transaction Coordinator (MSDTC) coordinates transactions that are distributed across two or more databases, message queues, file systems, or other transaction protected resource managers.  
 The service listens on TCP port 3372 along with a ephemeral TCP port (Above 1023).  
  
 Note one can disable the mutual authentication between the DTC services on different computers (In case the two computers are not on the same domain):
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\MSDTC \\Security\]  
>  TurnOffRpcSecurity=dword:00000001  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+827805+Q827805" rel="nofollow" title="BUG: MSDTC Fails to Mutually Authenticate When Computers Do Not Run in the Same Domain [Q827805]">MS KB827805</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+555017+Q555017" rel="nofollow" title="HOWTO: Enable DTC Between Web Servers and SQL Servers Running Windows Server 2003 [Q555017]">MS KB555017</a>

 Related [How to repair a broken MSDTC-log or reinstall MSDTC](/article/winnt-services-msdtc-config.html)  
  
 More Info <a href="https://www.bing.com/search?q=KB+243204+Q243204" rel="nofollow" title="Microsoft Distributed Transaction Coordinator (MSDTC) Recovery Techniques in Windows 2000 Cluster Server [Q243204]">MS KB243204</a>  
 More Info <a href="https://www.bing.com/search?q=KB+250367+Q250367" rel="nofollow" title="INFO: Configuring Microsoft Distributed Transaction Coordinator (DTC) to Work Through a Firewall [Q250367]">MS KB250367</a>  
 More Info <a href="https://www.bing.com/search?q=KB+252641+Q252641" rel="nofollow" title="Resolving MSDTC Conflicts During NTOP Installation on Cluster Server [Q252641]">MS KB252641</a>  
 More Info <a href="https://www.bing.com/search?q=KB+290624+Q290624" rel="nofollow" title="HOWTO: Configure MSDTC in a Windows 2000 Cluster Environment [Q290624]">MS KB290624</a>  
 More Info <a href="https://www.bing.com/search?q=KB+817064+Q817064" rel="nofollow" title="HOW TO: Enable Network DTC Access in Windows Server 2003 [Q817064]">MS KB817064</a>  
 More Info <a href="https://www.bing.com/search?q=KB+899191+Q899191" rel="nofollow" title="New functionality in the Distributed Transaction Coordinator service in Windows Server 2003 Service Pack 1 and in Windows XP Service Pack 2 [Q899191]">MS KB899191</a>  
  
##### Recommended State:

- Manual, if on a simple home network.

##### Default State:

- Win8/Win7/Vista: Manual.
- Win2k3: Automatic.
- WinXP: Manual.
- Win2k Srv.: Automatic.
- Win2k Pro.: Manual.

##### Process Name:

- msdtc.exe (MSDTC)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Security Accounts Manager](/article/winnt-services-samss.html)