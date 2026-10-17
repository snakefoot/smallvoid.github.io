---
title: 'Routing and Remote Access Service (RRAS)'
date: '2000-07-23T15:49:01+02:00'
permalink: /article/winnt-services-remoteaccess.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Routing and Remote Access service.'
type: post
id: 587
categories:
    - windows-2000_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
tags:
    - internet-connection-sharing
    - network-router
---
##### Description:

 The service offers:
- Routing service of LAN-to-LAN, LAN-to-WAN, virtual private network (VPN) and network address translation (NAT).  
   The routing possibilities of RRAS is more advanced than those provided by [Internet Connection Sharing](/article/winnt-services-sharedaccess.html) (Both using the same NAT module)
- Filtering according to filter rules which can be configured by tools like [NetSh](/article/winnt-netsh.html) and Routemon(WinNT4)
- Remote access via dial-up(PPP) and [VPN connections](/article/winnt-vpn.html). Related [Configure PPP/VPN MTU Size](/article/winnt-tcpip-mtu.html)
 
 When disabled the option "Incoming Connections" will disappear from "Network Connections" Control Panel.  
  
 More Info <a href="https://www.bing.com/search?q=KB+178993+Q178993" rel="nofollow" title="How to Use Static Routes with Routing and Remote Access Service [Q178993]">MS KB178993</a>  
 More Info <a href="https://www.bing.com/search?q=KB+234025+Q234025" rel="nofollow" title="Some Registry Entries Missing When Enabling Logging Features in RRAS [Q234025]">MS KB234025</a>  
 More Info <a href="https://www.bing.com/search?q=KB+241540+Q241540" rel="nofollow" title="OSPF over RRAS Dial-on-Demand and VPN Connections in Windows 2000 [Q241540]">MS KB241540</a>  
 More Info <a href="https://www.bing.com/search?q=KB+241545+Q241545" rel="nofollow" title="How to Implement RIP Over RRAS in Windows 2000 [Q241545]">MS KB241545</a>  
 More Info <a href="https://www.bing.com/search?q=KB+254322+Q254322" rel="nofollow" title="Conflicts Between Services Requesting Use of Network Address Translation Modules [Q254322]">MS KB254322</a>  
 More Info <a href="https://www.bing.com/search?q=KB+256644+Q256644" rel="nofollow" title="Description of Remote Access Wizards [Q256644]">MS KB256644</a>  
 More Info <a href="https://www.bing.com/search?q=KB+299801+Q299801" rel="nofollow" title="HOW TO: Configure a Windows 2000 Server as a Network Address Translation Server [Q299801]">MS KB299801</a>  
 More Info <a href="https://www.bing.com/search?q=KB+300434+Q300434" rel="nofollow" title="HOW TO: Allow Remote Users to Access Your Network in Windows 2000 [Q300434]">MS KB300434</a>  
 More Info <a href="https://www.bing.com/search?q=KB+313564+Q313564" rel="nofollow" title="HOW TO: Configure Routing and Remote Access Tracing in Windows 2000 [Q313564]">MS KB313564</a>  
 More Info <a href="https://www.bing.com/search?q=KB+321516+Q321516" rel="nofollow" title="How to Use the Windows 2000 Routing and Remote Access Service or ISA Server with a DSL Router for Internet Access [Q321516]">MS KB321516</a>  
 More Info <a href="https://www.bing.com/search?q=KB+816110+Q816110" rel="nofollow" title="HOW TO: Configure Routing and Remote Access Tracing in Windows Server 2003 [Q816110]">MS KB816110</a>  
 More Info <a href="https://www.bing.com/search?q=KB+816573+Q816573" rel="nofollow" title="HOW TO: Configure a VPN Server to Act as a Router in Windows Server 2003 [Q816573]">MS KB816573</a>  
 More Info <a href="https://www.bing.com/search?q=KB+816581+Q816581" rel="nofollow" title="ow to configure Network Address Translation in Windows Server 2003 [Q816581]">MS KB816581</a> (Replaces MS KB324264)  
  
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