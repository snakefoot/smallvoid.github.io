---
title: 'Internet Connection Sharing (ICS)'
date: '2000-07-23T19:48:58+02:00'
permalink: /article/winnt-services-sharedaccess.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Internet Connection Sharing (ICS) service.'
type: post
id: 803
categories:
    - windows-2000_services
    - windows-vista_services
    - windows-7-win7_services-guide
    - windows-8-win8_services-guide
tags:
    - internet-connection-sharing
    - NAT
    - network-router
---
##### Description:

 Provides network address translation (NAT), addressing and name resolution services for all computers on your home network, so they can access the Internet through the shared network- or dial-up- connection.  
  
 This service is mainly intended for home networks, and it includes its own DNS- and DHCP-Server, and makes use of the NAT module. If on a corporate network with own DNS-, DHCP-, RASS-Server, then ICS might conflict with these. One should instead use [Routing And Remote Access](/article/winnt-services-remoteaccess.html) or [ISA-Server](http://www.isaserver.org/) for providing access to the Internet.  
  
 Related [Setting up Internet Connection Sharing](/article/winnt-internet-connection-sharing.html)  
  
 More Info <a href="https://www.bing.com/search?q=KB%20234815%20Q234815" rel="nofollow" title="Description of Internet Connection Sharing [Q234815]">MS KB234815</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20250603%20Q250603" rel="nofollow" title="ICS May Not Function Properly with DNS or DHCP Server Services on the Same Computer [Q250603]">MS KB250603</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20310563%20Q310563" rel="nofollow" title="Description of Internet Connection Sharing in Windows XP [Q310563]">MS KB310563</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20827328%20Q827328" rel="nofollow" title="'Error 1068' Error Message When You Try to Turn On Internet Connection Sharing [Q827328]">MS KB827328</a>  
  
##### Recommended State:

- Disabled, if not sharing your internet connection.

##### Default State:

- Win8/Win7/Vista: Disabled.
- Win2k: Manual.

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (SharedAccess)

##### Supports:

- None

##### Depends:

- [Base Filtering Engine](/article/winnt-services-bfe.html) (Vista+)
- [Remote Access Connection Manager](/article/winnt-services-rasman.html)
- [Network Connections](/article/winnt-services-netman.html) (Vista+)
- [Windows Management Instrumentation](/article/winnt-services-winmgmt.html) (Vista+)