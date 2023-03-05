---
title: 'Setting up Internet Connection Sharing'
date: '2002-06-11T00:23:02+02:00'
status: publish
permalink: /article/winnt-internet-connection-sharing.html
author: Snakefoot
excerpt: 'How to configure Internet Connection Sharing to configure a gateway to the Internet for other computers.'
type: post
id: 430
category:
    - Network
    - Network
    - Network
    - Network
tag:
    - default-gateway
    - internet-connection-sharing
    - network-router
    - proxy
post_format: []
tags:
    - 'internet-connection-sharing,proxy,default-gateway,network-router'
---
For Win2k :

- Setup connection sharing :  
  [MS KB307311](http://support.microsoft.com/kb/307311 "HOW TO: Set Up Internet Connection Sharing in Windows 2000 [Q307311]") HOW TO: Set Up Internet Connection Sharing in Windows 2000  
  [MS KB237254](http://support.microsoft.com/kb/237254 "How to Enable Internet Connection Sharing on a Network Connection in Windows 2000 [Q237254]") How to Enable Internet Connection Sharing on a Network Connection in Windows 2000
- Forward ports to local server :  
  [MS Technet](http://www.microsoft.com/windows2000/en/professional/help/howto_share_conn_config.htm) To configure Internet connection sharing for applications and services
 
 For WinXP :
- Setup sharing of a connection :  
  [MS KB306126](http://support.microsoft.com/kb/306126 "HOW TO: Configure Internet Connection Sharing in Windows XP [Q306126]") HOW TO: Configure Internet Connection Sharing in Windows XP  
  [MS KB314066](http://support.microsoft.com/kb/314066 "How to Enable Internet Connection Sharing on a Home or Small Office Network Connection in Windows XP [Q314066]") How to Enable Internet Connection Sharing on a Home or Small Office Network Connection in Windows XP
- Setup sharing of a PPPoE connection :  
  [MS KB316276](http://support.microsoft.com/kb/316276 "How to Share a PPPoE Internet Connection with Windows XP [Q316276]") How to Share a PPPoE Internet Connection with Windows XP  
  [MS KB319661](http://support.microsoft.com/kb/319661 "Connectivity Problems on ICS Clients When You Use a PPPoE Connection on a Windows XP ICS Host [Q319661]") Connectivity Problems on ICS Clients When You Use a PPPoE Connection on a Windows XP ICS Host
- Use static IP on local server :  
  [MS KB309642](http://support.microsoft.com/kb/309642 "How to Configure a Static Client for Windows XP Internet Connection Sharing [Q309642]") How to Configure a Static Client for Windows XP Internet Connection Sharing
- Forward ports to local server :  
  [MS KB309524](http://support.microsoft.com/kb/309524 "How to Configure Windows XP ICS for an Internal PPTP Server [Q309524]") How to Configure Windows XP ICS for an Internal PPTP Server
- Create bridge with connection sharing :  
  [MS KB309640](http://support.microsoft.com/kb/309640 "Creating a Bridge with Two Internal Adapters on a Windows XP Internet Connection Sharing Host Does Not Work [Q309640]") Creating a Bridge with Two Internal Adapters on ICS Host  
  [MS KB302348](http://support.microsoft.com/kb/302348 "Bridge May Not Work With a Non-Promiscuous Mode Network Adapter [Q302348]") Bridge May Not Work With a Non-Promiscuous Mode Network Adapter  
  [MS KB892892](http://support.microsoft.com/kb/892892 "You cannot enable the Network Bridge connection between network adaptors in Windows XP [Q892892]") Bridge between network adapters may not enable in Windows XP
- Troubleshoot the connection sharing :  
  [MS KB308021](http://support.microsoft.com/kb/308021 "Resources for Troubleshooting Internet Connection Sharing in Windows XP [Q308021]") Resources for Troubleshooting Internet Connection Sharing in Windows XP
 
 For Win2k3:
- Setup connection sharing :  
  [MS KB324286](http://support.microsoft.com/kb/324286 "HOW TO: Set Up Internet Connection Sharing in Windows Server 2003 [Q324286]") HOW TO: Set Up Internet Connection Sharing in Windows Server 2003
 
 Note to do ICS in WinNT4 a proxy server has to be installed:
- [Microsoft Internet Security and Acceleration (ISA)](http://www.microsoft.com/isaserver/), which tries to replace [Microsoft Proxy Server](http://msdn.microsoft.com/library/en-us/dnntpro00/html/MSProxy.asp)
- [AnalogX Proxy](http://www.analogx.com/contents/download/network/proxy.htm) (Freeware)
- [VSocks Light](http://www.pscs.co.uk/products/vsockslight/) (Freeware)
- [FreeProxy](http://www.alphalink.com.au/~gregr/freeproxy.htm) (Freeware)
- [WinRoute](http://www.winroute.com/)
- [WinGate](http://www.wingate.net/)
- [Nat32](http://www.nat32.com/)
 
 Related [Internet Connection Sharing in Win98/Me](/article/win9x-internet-connection-sharing.html)