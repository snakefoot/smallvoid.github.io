---
title: 'Configure the priority of networks known by the MUP'
date: '2003-12-30T23:05:45+01:00'
status: publish
permalink: /article/winnt-network-priority.html
author: Snakefoot
excerpt: 'Change which network redirector to use first when looking for a resource on the network.'
type: post
id: 419
category:
    - Network
    - Network
    - Network
    - Network
tag:
    - distributed-file-system
    - network-redirector
    - novell-network
post_format: []
tags:
    - 'network-redirector,novell-network,distributed-file-system'
---
The following happens when an application requests a network resource using the Uniform Naming Convention (UNC):

1. The request is received by the Multiple UNC Provider (MUP)
2. The MUP checks it's cache for a recent handle to the wanted resource (Since the last 15 Minutes) if available it is returned
3. The MUP goes through the available network redirectors and ask them if they know the wanted resource (Sorted by priority)
4. Each network redirector responds back with a handle to the wanted resource if available (Asked synchronously)
5. The MUP returns the handle from the redirector which responds back first (Highest priority).
 
 One should make sure the redirectors/providers (Like "Microsoft Client for Microsoft Networks" or "Novell Client for Novell Netware"), which knows the majority of the wanted network resources, has the highest priority.  
  
 To configure the priority of redirectors in WinNT4:
1. Open **Control Panel**
2. Double click **Network** applet
3. Select **Services** tab
4. Click **Network Access Order**
 
 To configure the priority of redirectors in Win2k/WinXP:
1. Open **Control Panel**
2. Double click **Network and Dial-Up Connections**
3. In the menu select **Advanced** and select **Advanced Settings...**
  - Vista will only display the Advanced menu-item when pressing the ALT-key
4. Select the **Provider Order** tab and set the priority of **Network Providers**
 
 Note by default the [Distributed File System (DFS)](/article/winnt-services-dfs.html) is always asked first (Independent of priority), this can be disabled with this registry key (Causes [BSOD with the Mup.sys in Win2k SP4 (MS KB824288)](http://support.microsoft.com/kb/824288))
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Mup\]  
>  DisableDfs = 1 (Default = 0)  
>   
>  More Info [MS KB259398](http://support.microsoft.com/kb/259398 "SceCli Event ID 1001 and UserEnv Event ID 1000 When Dfs Client Is Disabled [Q259398]")  
>  More Info [MS KB314494](http://support.microsoft.com/kb/314494 "Group Policies Are Not Applied The Way You Expect; "Event ID 1058" and "Event ID 1030" Errors in the Application Log [Q314494]")

 Note MUP.SYS is usually the last driver being shown before launching the operating system, and if there is a problem with loading Windows, then it might seem like MUP.SYS is causing the problem (But it is not).  
  
 More Info [MS KB171386](http://support.microsoft.com/kb/171386 "Connectivity Delay with Multiple Redirectors Installed [Q171386]")  
  
 Related [Configure the priority of network adapter and gateways](/article/network-gateway-metric.html)  
 Related [Configure the priority of protocols bound to the network redirector](/article/winnt-protocol-priority.html)  