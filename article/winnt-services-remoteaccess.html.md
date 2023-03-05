---
title: 'Routing and Remote Access Service (RRAS)'
date: '2000-07-23T15:49:01+02:00'
status: publish
permalink: /article/winnt-services-remoteaccess.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Routing and Remote Access service.'
type: post
id: 587
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - internet-connection-sharing
    - network-router
post_format: []
tags:
    - 'internet-connection-sharing,network-router'
---
##### Description:

 The service offers: - Routing service of LAN-to-LAN, LAN-to-WAN, virtual private network (VPN) and network address translation (NAT).  
   The routing possibilities of RRAS is more advanced than those provided by [Internet Connection Sharing](/article/winnt-services-sharedaccess.html) (Both using the same NAT module)
- Filtering according to filter rules which can be configured by tools like [NetSh](/article/winnt-netsh.html) and Routemon(WinNT4)
- Remote access via dial-up(PPP) and [VPN connections](/article/winnt-vpn.html). Related [Configure PPP/VPN MTU Size](/article/winnt-tcpip-mtu.html)
 
 When disabled the option "Incoming Connections" will disappear from "Network Connections" Control Panel.  
  
 More Info [MS KB178993](http://support.microsoft.com/kb/178993 "How to Use Static Routes with Routing and Remote Access Service [Q178993]")  
 More Info [MS KB234025](http://support.microsoft.com/kb/234025 "Some Registry Entries Missing When Enabling Logging Features in RRAS [Q234025]")  
 More Info [MS KB241540](http://support.microsoft.com/kb/241540 "OSPF over RRAS Dial-on-Demand and VPN Connections in Windows 2000 [Q241540]")  
 More Info [MS KB241545](http://support.microsoft.com/kb/241545 "How to Implement RIP Over RRAS in Windows 2000 [Q241545]")  
 More Info [MS KB254322](http://support.microsoft.com/kb/254322 "Conflicts Between Services Requesting Use of Network Address Translation Modules [Q254322]")  
 More Info [MS KB256644](http://support.microsoft.com/kb/256644 "Description of Remote Access Wizards [Q256644]")  
 More Info [MS KB299801](http://support.microsoft.com/kb/299801 "HOW TO: Configure a Windows 2000 Server as a Network Address Translation Server [Q299801]")  
 More Info [MS KB300434](http://support.microsoft.com/kb/300434 "HOW TO: Allow Remote Users to Access Your Network in Windows 2000 [Q300434]")  
 More Info [MS KB313564](http://support.microsoft.com/kb/313564 "HOW TO: Configure Routing and Remote Access Tracing in Windows 2000 [Q313564]")  
 More Info [MS KB321516](http://support.microsoft.com/kb/321516 "How to Use the Windows 2000 Routing and Remote Access Service or ISA Server with a DSL Router for Internet Access [Q321516]")  
 More Info [MS KB816110](http://support.microsoft.com/kb/816110 "HOW TO: Configure Routing and Remote Access Tracing in Windows Server 2003 [Q816110]")  
 More Info [MS KB816573](http://support.microsoft.com/kb/816573 "HOW TO: Configure a VPN Server to Act as a Router in Windows Server 2003 [Q816573]")  
 More Info [MS KB816581](http://support.microsoft.com/kb/816581 "ow to configure Network Address Translation in Windows Server 2003 [Q816581]") (Replaces MS KB324264)  
  
##### Recommended State:

- Disabled, for security measures so it will not be listening for incoming remote request.
- Manual, if using a Virtual Private Network(VPN) or if acting like a router/proxy.

##### Default State:

- Win8/Win7/Vista: Disabled
- Win2k3: Disabled
- WinXP SP2: Disabled
- WinXP: Manual
- Win2k: Disabled

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (RemoteAccess)

##### Supports:

- None

##### Depends:

- [Base Filtering Engine](/article/winnt-services-bfe.html) (Vista+)
- NetBIOSGroup
- [Remote Access Connection Manager](/article/winnt-services-rasman.html) (Vista+)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Remote Registry Service](/article/winnt-services-remoteregistry.html) (Unofficial)