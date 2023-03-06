---
title: 'Fails to obtain IP address when using DHCP broadcast request'
date: '2007-09-06T00:55:27+02:00'
status: publish
permalink: /article/vista-dhcp-client-broadcast.html
author: Snakefoot
excerpt: 'Certain network routers doesn''t respond to DHCP requests that requires broadcast reply.'
type: post
id: 741
category:
    - Network
tag:
    - dhcp
post_format: []
tags:
    - dhcp
---
Windows Vista changes the behavior of the [DHCP Client](/article/winnt-services-dhcp.html) (Compared to XP SP2), and now tells the server to respond using broadcast (multicast instead of unicast). This change allows Vista to obtain an IP address even if not connected to the same subnet as the DHCP server.  
  
 Many network routers also acts as DHCP servers, and some of them ignores DHCP requests with the broadcast flag set. If the client sends such a DHCP request, then the client will fail to receive a response and will not aquire a proper IP address. The solution is either to upgrade / replace the network router, or configure the DHCP client so it will not set the broadcast flag.  
  
 Configure the following DWORD registry value to make Windows first try with DHCP broadcast, and if that fails then fall back to not use DHCP broadcast:

 > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters \\Interfaces \\{GUID}\]  
 >  DhcpConnEnableBcastFlagToggle = 1 (Default = 0)  
 >   
 >  More Info [MS KB928233](http://support.microsoft.com/kb/928233 "Windows Vista cannot obtain an IP address from certain routers or from certain non-Microsoft DHCP servers")

 Configure the following DWORD registry value to disable the use of DHCP broadcast completely:
 
 > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters \\Interfaces \\{GUID}\]  
 >  DhcpConnForceBroadcastFlag = 0 (Default = 1)  
 >  
 > More Info [MS KB928233](http://support.microsoft.com/kb/928233 "Windows Vista cannot obtain an IP address from certain routers or from certain non-Microsoft DHCP servers")

 More Info [MS KB932134](http://support.microsoft.com/kb/932134 "An outdated network router may not function correctly when you use it together with new networking features in Windows Vista") (Online tool to test network router)
 
##### What about DhcpConnDisableBcastFlagToggle ?

 Microsoft made a spelling mistakes the first time they described the registry key to disable the DHCP broadcast request. They mistakenly wrote DhcpConnDisableBcastFlagToggle instead of DhcpConnEnableBcastFlagToggle.