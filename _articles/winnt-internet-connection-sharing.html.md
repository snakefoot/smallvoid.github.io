---
title: 'Setting up Internet Connection Sharing'
date: '2002-06-11T00:23:02+02:00'
permalink: /article/winnt-internet-connection-sharing.html
author: Snakefoot
excerpt: 'How to configure Internet Connection Sharing to configure a gateway to the Internet for other computers.'
type: post
id: 430
categories:
    - windows-nt4_network
    - windows-xp_network
    - windows-2000_network
    - windows-2003_network
tags:
    - default-gateway
    - internet-connection-sharing
    - network-router
    - proxy
---
For Win2k :

- Setup connection sharing :  
  <a href="https://www.bing.com/search?q=KB+307311+Q307311" rel="nofollow" title="HOW TO: Set Up Internet Connection Sharing in Windows 2000 [Q307311]">MS KB307311</a> HOW TO: Set Up Internet Connection Sharing in Windows 2000  
  <a href="https://www.bing.com/search?q=KB+237254+Q237254" rel="nofollow" title="How to Enable Internet Connection Sharing on a Network Connection in Windows 2000 [Q237254]">MS KB237254</a> How to Enable Internet Connection Sharing on a Network Connection in Windows 2000
- Forward ports to local server :  
  [MS Technet](http://www.microsoft.com/windows2000/en/professional/help/howto_share_conn_config.htm) To configure Internet connection sharing for applications and services
 
 For WinXP :
- Setup sharing of a connection :  
  <a href="https://www.bing.com/search?q=KB+306126+Q306126" rel="nofollow" title="HOW TO: Configure Internet Connection Sharing in Windows XP [Q306126]">MS KB306126</a> HOW TO: Configure Internet Connection Sharing in Windows XP  
  <a href="https://www.bing.com/search?q=KB+314066+Q314066" rel="nofollow" title="How to Enable Internet Connection Sharing on a Home or Small Office Network Connection in Windows XP [Q314066]">MS KB314066</a> How to Enable Internet Connection Sharing on a Home or Small Office Network Connection in Windows XP
- Setup sharing of a PPPoE connection :  
  <a href="https://www.bing.com/search?q=KB+316276+Q316276" rel="nofollow" title="How to Share a PPPoE Internet Connection with Windows XP [Q316276]">MS KB316276</a> How to Share a PPPoE Internet Connection with Windows XP  
  <a href="https://www.bing.com/search?q=KB+319661+Q319661" rel="nofollow" title="Connectivity Problems on ICS Clients When You Use a PPPoE Connection on a Windows XP ICS Host [Q319661]">MS KB319661</a> Connectivity Problems on ICS Clients When You Use a PPPoE Connection on a Windows XP ICS Host
- Use static IP on local server :  
  <a href="https://www.bing.com/search?q=KB+309642+Q309642" rel="nofollow" title="How to Configure a Static Client for Windows XP Internet Connection Sharing [Q309642]">MS KB309642</a> How to Configure a Static Client for Windows XP Internet Connection Sharing
- Forward ports to local server :  
  <a href="https://www.bing.com/search?q=KB+309524+Q309524" rel="nofollow" title="How to Configure Windows XP ICS for an Internal PPTP Server [Q309524]">MS KB309524</a> How to Configure Windows XP ICS for an Internal PPTP Server
- Create bridge with connection sharing :  
  <a href="https://www.bing.com/search?q=KB+309640+Q309640" rel="nofollow" title="Creating a Bridge with Two Internal Adapters on a Windows XP Internet Connection Sharing Host Does Not Work [Q309640]">MS KB309640</a> Creating a Bridge with Two Internal Adapters on ICS Host  
  <a href="https://www.bing.com/search?q=KB+302348+Q302348" rel="nofollow" title="Bridge May Not Work With a Non-Promiscuous Mode Network Adapter [Q302348]">MS KB302348</a> Bridge May Not Work With a Non-Promiscuous Mode Network Adapter  
  <a href="https://www.bing.com/search?q=KB+892892+Q892892" rel="nofollow" title="You cannot enable the Network Bridge connection between network adaptors in Windows XP [Q892892]">MS KB892892</a> Bridge between network adapters may not enable in Windows XP
- Troubleshoot the connection sharing :  
  <a href="https://www.bing.com/search?q=KB+308021+Q308021" rel="nofollow" title="Resources for Troubleshooting Internet Connection Sharing in Windows XP [Q308021]">MS KB308021</a> Resources for Troubleshooting Internet Connection Sharing in Windows XP
 
 For Win2k3:
- Setup connection sharing :  
  <a href="https://www.bing.com/search?q=KB+324286+Q324286" rel="nofollow" title="HOW TO: Set Up Internet Connection Sharing in Windows Server 2003 [Q324286]">MS KB324286</a> HOW TO: Set Up Internet Connection Sharing in Windows Server 2003
 
 Note to do ICS in WinNT4 a proxy server has to be installed:
- [Microsoft Internet Security and Acceleration (ISA)](http://www.microsoft.com/isaserver/), which tries to replace [Microsoft Proxy Server](http://msdn.microsoft.com/library/en-us/dnntpro00/html/MSProxy.asp)
- [AnalogX Proxy](http://www.analogx.com/contents/download/network/proxy.htm) (Freeware)
- [VSocks Light](http://www.pscs.co.uk/products/vsockslight/) (Freeware)
- [FreeProxy](http://www.alphalink.com.au/~gregr/freeproxy.htm) (Freeware)
- [WinRoute](http://www.winroute.com/)
- [WinGate](http://www.wingate.net/)
- [Nat32](http://www.nat32.com/)
 
 Related [Internet Connection Sharing in Win98/Me](/article/win9x-internet-connection-sharing.html)