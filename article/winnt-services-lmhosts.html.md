---
title: 'TCP/IP NetBIOS Helper Service'
date: '2000-06-06T19:15:40+02:00'
status: publish
permalink: /article/winnt-services-lmhosts.html
author: Snakefoot
excerpt: 'Description and recommended settings for the TCP/IP NetBIOS Helper service.'
type: post
id: 602
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - hosts-file
    - lmhosts
    - netbios
post_format: []
tags:
    - 'netbios,lmhosts,hosts-file'
---
##### Description:

 Enables support for NetBIOS over TCP/IP (NetBT) service and NetBIOS name resolution. Is used for resolving Fully Qualified Domain Name (FQDN) in Universal Naming Convention(UNC) for NetBios over Tcpip (NetBT) to find the actual physical address.  
  
 Note if using netbios to logon to the domain and this service is disabled, then the Group Policy will not be applied to the machine.  
  
 Note if wanting to change the location of the lmhosts file (Along with [hosts](/article/windows-hosts-file.html), services, networks, protocols, NETRC files) then change this STRING registry value:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  DataBasePath = "C:\\Etc"

 More Info [MS KB101927](http://support.microsoft.com/kb/101927 "The Lmhosts File for TCP/IP in Windows [Q101927]")  
 More Info [MS KB105997](http://support.microsoft.com/kb/105997 "Differences Between the HOSTS and LMHOSTS Files in Windows NT [Q105997]")  
 More Info [MS KB180094](http://support.microsoft.com/kb/180094 "How to Write an LMHOSTS File for Domain Validation and Other Name Resolution Issues [Q180094]")  
 More Info [MS KB180099](http://support.microsoft.com/kb/180099 "Troubleshooting LMHOSTS Name Resolution Issues [Q180099]")  
 More Info [MS KB314108](http://support.microsoft.com/kb/314108 "How to Write an LMHOSTS File for Domain Validation and Other Name Resolution Issues [Q314108]")  
  
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