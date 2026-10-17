---
title: 'Universal Plug and Play (UPnP) Device Host'
date: '2003-06-05T20:02:10+02:00'
permalink: /article/winnt-services-upnphost.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Universal Plug and Play Device Host service.'
type: post
id: 610
categories:
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
tags: []
---
##### Description:

 Provides support to host [Universal Plug and Play (UPnP)](http://www.upnp.org/) devices. UPnP is an extension for working with PnP-devices not attached directly to the computer but accessed through the network. (Like networked Printers/Scanners/Gateways etc.)  
  
 Note that UPnP can be uninstalled through the Control Panel -&gt; Add/Remove-Programs.  
  
 Note if using Internet Connection Sharing then this service should be started on the server and the clients (If WinXP) as it will provides the ability to see the Gateway icon on the clients.  
  
 Note if having problem getting online with MSN Messenger or a DirectX game, then one might have to enable this service to make it work.  
  
 Note if this service is disabled and using Windows Media Player 11, then it will give this error:
> Event ID - 10005  
>  Description - DCOM got error "The service cannot be started, either because it is disabled or because it has no enabled devices associated with it. " attempting to start the service upnphost with arguments "" in order to run the server: {204810B9-73B2-11D4-BF42-00B0D0118B56}

 More Info <a href="https://www.bing.com/search?q=KB+315000+Q315000" rel="nofollow" title="Unchecked Buffer in Universal Plug and Play Can Lead to System Compromise for Windows XP [Q315000]">MS KB315000</a>  
 More Info <a href="https://www.bing.com/search?q=KB+315056+Q315056" rel="nofollow" title="Preventing Distributed Denial-of-Service Attacks that Use the Universal Plug-and-Play Service [Q315056]">MS KB315056</a>  
 More Info <a href="https://www.bing.com/search?q=KB+317843+Q317843" rel="nofollow" title="Traffic Is Sent After You Turn Off the SSDP Discover Service and Universal Plug and Play Device Host [Q317843]">MS KB317843</a>  
 More Info <a href="https://www.bing.com/search?q=KB+323713+Q323713" rel="nofollow" title="Description of Universal Plug and Play Features in Windows XP [Q323713]">MS KB323713</a>  
 More Info [Universal Plug and Play in Windows XP](http://www.microsoft.com/windowsxp/pro/techinfo/planning/upnp/default.asp "Windows XP : Technical Resources : Planning")  
  
##### Recommended State:

- Disabled, unless working with networked Universal Plug and Play devices or using [Internet Connection Sharing](/article/winnt-services-sharedaccess.html).

##### Default State:

- Win7 - Manual
- Vista: Automatic
- WinXP: Manual

##### Process Name:

- Win7 - [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (UPNPhost)
- WinXP/Vista - [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (UPNPhost)

##### Supports:

- [Internet Connection Sharing](/article/winnt-services-sharedaccess.html) (Unoffically)
- [Windows Media Player Network Sharing Service](/article/winnt-services-wmpnetworksvc.html) (Vista only)

##### Depends:

- [SSDP Discovery Service](/article/winnt-services-ssdpsrv.html)