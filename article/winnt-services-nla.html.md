---
title: 'Network Location Awareness'
date: '2003-06-05T15:37:47+02:00'
status: publish
permalink: /article/winnt-services-nla.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Network Location Awareness service.'
type: post
id: 568
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Collects and stores network configuration and location information, and notifies applications when this information changes.  
  
 For example, a wireless computer roaming between physical networks can use NLA to determine the proper configuration based on information about its available network connection.  
 NLA also proves valuable when a multihomed computer has a physical connection to one network while also connected to another network through a dial-up connection or a tunnel.  
  
##### Recommended State:

- Automatic

##### Default State:

- Win8/Win7/Vista: Automatic.
- WinXP: Manual.
- Win2k3: Manual.

##### Process Name:

- Win8/Win7/Vista: [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (Nla)
- WinXP/Win2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Nla)

##### Supports:

- [Internet Connection Firewall &amp; Internet Connection Sharing](/article/winnt-services-sharedaccess.html) (WinXP/Win2k3 only)
- [Network List Service](/article/winnt-services-netprofm.html) (Vista+)
- [WWAN AutoConfig](/article/winnt-services-wwansvc.html) (Win7 only)

##### Depends:

- [Network Store Interface Service](/article/winnt-services-nsi.html) (Vista+)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) (Vista+)
- [DHCP Client](/article/winnt-services-dhcp.html) (Win8+)