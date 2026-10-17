---
title: 'SSDP Discovery Service'
date: '2003-06-05T19:00:01+02:00'
permalink: /article/winnt-services-ssdpsrv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the SSDP Discovery service.'
type: post
id: 599
categories:
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
tags: []
---
##### Description:

 The Simple Service Discovery Protocol (SSDP) enables detection of Universal Plug and Play (UPnP) devices on your home network. This service listens for UPnP connections at TCP port 5000 and UDP port 1900.  
 UPnP devices can for example be printers or Internet Gateway Devices (IGD) like routers, firewalls or computers running Internet Connection Sharing. When contact have been made to an UPnP device, then it is possible for the UPnP device to respond what it can be used for.  
  
 Note if using Internet Connection Sharing then this service should be started on the server and the clients (If WinXP) as it will provides the ability to see the Gateway icon on the clients.  
  
 Note even if having disabled this service, then SSDP traffic might still occur. This can be caused by applications like MSN Messenger. To disable SSDP completely, one also have to set this registry key:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\DirectPlayNATHelp \\DPNHUPnP\]  
>  UPnPMode = 2  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+317843+Q317843" rel="nofollow" title="Traffic Is Sent After You Turn Off the SSDP Discover Service and Universal Plug and Play Device Host [Q317843]">MS KB317843</a>

 More Info <a href="https://www.bing.com/search?q=KB+315056+Q315056" rel="nofollow" title="Preventing Distributed Denial-of-Service Attacks that Use the Universal Plug-and-Play Service [Q315056]">MS KB315056</a>  
 More Info <a href="https://www.bing.com/search?q=KB+821371+Q821371" rel="nofollow" title="Capabilities of the Internet Gateway Device Discovery and Control Client and of Universal Plug and Play">MS KB821371</a>  
 More Info <a href="https://www.bing.com/search?q=KB+821980+Q821980" rel="nofollow" title="The Internet Gateway Device Discovery and Control Client Is an Optional Networking Component in Windows XP Professional Service Pack 1a (SP1a)">MS KB821980</a> (How to uninstall gateway discovery)  
  
##### Recommended State:

- Disabled, unless working with networked Universal Plug and Play devices or using [Internet Connection Sharing](/article/winnt-services-sharedaccess.html).

##### Default State:

- Manual.

##### Process Name:

- Win7 - [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (SSDPSRV)
- WinXP/Vista - [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (SSDPSRV)

##### Supports:

- [Universal Plug and Play Device Host](/article/winnt-services-upnphost.html)
- [Internet Connection Sharing](/article/winnt-services-sharedaccess.html) (Unofficially)
- [Windows Media Center Extender Service](/article/winnt-services-mcx2svc.html) (Vista+)

##### Depends:

- None