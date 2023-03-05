---
title: 'Internet Connection Firewall (ICF)/Internet Connection Sharing (ICS)'
date: '2000-07-23T02:20:12+02:00'
status: publish
permalink: /article/winxp-services-sharedaccess.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Firewall/Internet Connection Sharing (ICS) service.'
type: post
id: 553
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - default-gateway
    - firewall
    - internet-connection-sharing
    - network-router
    - VPN
post_format: []
tags:
    - 'internet-connection-sharing,default-gateway,VPN,firewall,network-router'
---
##### Description:

 Provides network address translation (NAT), addressing and name resolution services for all computers on your home network, so they can access the Internet through the shared network- or dial-up- connection.  
  
 This service is mainly intended for home networks, and it includes its own DNS- and DHCP-Server, and makes use of the NAT module. If on a corporate network with own DNS-, DHCP-, RASS-Server, then ICS might conflict with these. One should instead use [Routing And Remote Access](/article/winnt-services-remoteaccess.html) or [ISA-Server](http://www.isaserver.org/) for providing access to the Internet.  
  
 Note with Windows XP this service has been extended with a software firewall that can block incoming traffic. The firewall is activated by default when running WinXP Service Pack 2, and will provide enough protection for most users, but if also wanting full control of outgoing traffic, then a 3rd party firewall is required.  
  
 Related [Setting up Internet Connection Sharing](/article/winnt-internet-connection-sharing.html)  
 Related [Setting up WinXP Internet Connection Firewall (ICF)](/article/winxp-firewall.html)  
 Related [How to repair the Windows Firewall service if it will not start](/article/winnt-firewall-ics-config.html)  
  
 More Info [MS KB234815](http://support.microsoft.com/kb/234815 "Description of Internet Connection Sharing [Q234815]")  
 More Info [MS KB250603](http://support.microsoft.com/kb/250603 "ICS May Not Function Properly with DNS or DHCP Server Services on the Same Computer [Q250603]")  
 More Info [MS KB310563](http://support.microsoft.com/kb/310563 "Description of Internet Connection Sharing in Windows XP [Q310563]")  
 More Info [MS KB310563](http://support.microsoft.com/kb/310563 "HOW TO: Turn On the Internet Connection Firewall Feature in Windows Server 2003 [Q310563]")  
 More Info [MS KB827328](http://support.microsoft.com/kb/827328 ""Error 1068" Error Message When You Try to Turn On Internet Connection Sharing [Q827328]")  
  
##### Recommended State:

- Disabled, if not sharing your internet connection AND not using the builtin firewall.
- Automatic, if using the builtin firewall or connection sharing.

##### Default State:

- WinXP: Automatic.
- Win2k3: Disabled.

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (SharedAccess)

##### Supports:

- None

##### Depends:

- [Remote Access Connection Manager](/article/winnt-services-rasman.html)
- [Application Layer Gateway](/article/winnt-services-alg.html) (WinXP+)
- [Network Connections](/article/winnt-services-netman.html) (WinXP+)
- [Network Location Awareness](/article/winnt-services-nla.html) (WinXP+)
- [Remote Access Auto Connection Manager](/article/winnt-services-rasauto.html) (Win2k3+)
- [Universal Plug and Play Device Host](/article/winnt-services-upnphost.html) (WinXP+ - unofficially)
- [SSDP Discovery](/article/winnt-services-ssdpsrv.html) (WinXP+ - unofficially)