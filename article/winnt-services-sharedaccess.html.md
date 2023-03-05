---
title: 'Internet Connection Sharing (ICS)'
date: '2000-07-23T19:48:58+02:00'
status: publish
permalink: /article/winnt-services-sharedaccess.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Internet Connection Sharing (ICS) service.'
type: post
id: 803
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - internet-connection-sharing
    - NAT
    - network-router
post_format: []
tags:
    - 'internet-connection-sharing,NAT,network-router'
---
##### Description:

 Provides network address translation (NAT), addressing and name resolution services for all computers on your home network, so they can access the Internet through the shared network- or dial-up- connection.  
  
 This service is mainly intended for home networks, and it includes its own DNS- and DHCP-Server, and makes use of the NAT module. If on a corporate network with own DNS-, DHCP-, RASS-Server, then ICS might conflict with these. One should instead use [Routing And Remote Access](/article/winnt-services-remoteaccess.html) or [ISA-Server](http://www.isaserver.org/) for providing access to the Internet.  
  
 Related [Setting up Internet Connection Sharing](/article/winnt-internet-connection-sharing.html)  
  
 More Info [MS KB234815](http://support.microsoft.com/kb/234815 "Description of Internet Connection Sharing [Q234815]")  
 More Info [MS KB250603](http://support.microsoft.com/kb/250603 "ICS May Not Function Properly with DNS or DHCP Server Services on the Same Computer [Q250603]")  
 More Info [MS KB310563](http://support.microsoft.com/kb/310563 "Description of Internet Connection Sharing in Windows XP [Q310563]")  
 More Info [MS KB827328](http://support.microsoft.com/kb/827328 ""Error 1068" Error Message When You Try to Turn On Internet Connection Sharing [Q827328]")  
  
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