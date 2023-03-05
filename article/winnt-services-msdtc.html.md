---
title: 'Distributed Transaction Coordinator'
date: '2000-07-23T01:17:01+02:00'
status: publish
permalink: /article/winnt-services-msdtc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Distributed Transaction Coordinator service.'
type: post
id: 540
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Distributed Transaction Coordinator (MSDTC) coordinates transactions that are distributed across two or more databases, message queues, file systems, or other transaction protected resource managers.  
 The service listens on TCP port 3372 along with a ephemeral TCP port (Above 1023).  
  
 Note one can disable the mutual authentication between the DTC services on different computers (In case the two computers are not on the same domain):
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\MSDTC \\Security\]  
>  TurnOffRpcSecurity=dword:00000001  
>   
>  More Info [MS KB827805](http://support.microsoft.com/kb/827805 "BUG: MSDTC Fails to Mutually Authenticate When Computers Do Not Run in the Same Domain [Q827805]")  
>  More Info [MS KB555017](http://support.microsoft.com/kb/555017 "HOWTO: Enable DTC Between Web Servers and SQL Servers Running Windows Server 2003 [Q555017]")

 Related [How to repair a broken MSDTC-log or reinstall MSDTC](/article/winnt-services-msdtc-config.html)  
  
 More Info [MS KB243204](http://support.microsoft.com/kb/243204 "Microsoft Distributed Transaction Coordinator (MSDTC) Recovery Techniques in Windows 2000 Cluster Server [Q243204]")  
 More Info [MS KB250367](http://support.microsoft.com/kb/250367 "INFO: Configuring Microsoft Distributed Transaction Coordinator (DTC) to Work Through a Firewall [Q250367]")  
 More Info [MS KB252641](http://support.microsoft.com/kb/252641 "Resolving MSDTC Conflicts During NTOP Installation on Cluster Server [Q252641]")  
 More Info [MS KB290624](http://support.microsoft.com/kb/290624 "HOWTO: Configure MSDTC in a Windows 2000 Cluster Environment [Q290624]")  
 More Info [MS KB817064](http://support.microsoft.com/kb/817064 "HOW TO: Enable Network DTC Access in Windows Server 2003 [Q817064]")  
 More Info [MS KB899191](http://support.microsoft.com/kb/899191 "New functionality in the Distributed Transaction Coordinator service in Windows Server 2003 Service Pack 1 and in Windows XP Service Pack 2 [Q899191]")  
  
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