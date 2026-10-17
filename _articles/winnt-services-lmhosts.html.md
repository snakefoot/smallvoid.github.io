---
title: 'TCP/IP NetBIOS Helper Service'
date: '2000-06-06T19:15:40+02:00'
permalink: /article/winnt-services-lmhosts.html
author: Snakefoot
excerpt: 'Description and recommended settings for the TCP/IP NetBIOS Helper service.'
type: post
id: 602
categories:
    - windows-2000_services
    - windows-nt4_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
tags:
    - hosts-file
    - lmhosts
    - netbios
---
##### Description:

 Enables support for NetBIOS over TCP/IP (NetBT) service and NetBIOS name resolution. Is used for resolving Fully Qualified Domain Name (FQDN) in Universal Naming Convention(UNC) for NetBios over Tcpip (NetBT) to find the actual physical address.  
  
 Note if using netbios to logon to the domain and this service is disabled, then the Group Policy will not be applied to the machine.  
  
 Note if wanting to change the location of the lmhosts file (Along with [hosts](/article/windows-hosts-file.html), services, networks, protocols, NETRC files) then change this STRING registry value:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  DataBasePath = "C:\\Etc"

 More Info <a href="https://www.bing.com/search?q=KB%20101927%20Q101927" rel="nofollow" title="The Lmhosts File for TCP/IP in Windows [Q101927]">MS KB101927</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20105997%20Q105997" rel="nofollow" title="Differences Between the HOSTS and LMHOSTS Files in Windows NT [Q105997]">MS KB105997</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20180094%20Q180094" rel="nofollow" title="How to Write an LMHOSTS File for Domain Validation and Other Name Resolution Issues [Q180094]">MS KB180094</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20180099%20Q180099" rel="nofollow" title="Troubleshooting LMHOSTS Name Resolution Issues [Q180099]">MS KB180099</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20314108%20Q314108" rel="nofollow" title="How to Write an LMHOSTS File for Domain Validation and Other Name Resolution Issues [Q314108]">MS KB314108</a>  
  
##### Recommended State:

- Disabled, if on a simple home network (Even if using Netbios over TcpIp).
- Automatic, if needing to login on to a domain using Netbios/WINS or using the LmHosts-file.

##### Default State:

- Automatic

##### Process Name:

- Win2k: [services.exe](/article/winnt-services-wrapper.html) (LmHosts)
- WinXP/Win2k3: [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (LmHosts)
- Vista/Win7: [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (LmHosts)

##### Supports:

- [Computer Browser](/article/winnt-services-browser.html) (WinNT4 only)

##### Depends:

- None