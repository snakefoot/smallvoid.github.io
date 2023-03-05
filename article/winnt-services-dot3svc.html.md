---
title: 'Wired AutoConfig'
date: '2007-07-17T00:18:35+02:00'
status: publish
permalink: /article/winnt-services-dot3svc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Wired AutoConfig service.'
type: post
id: 729
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Performs IEEE 802.1X authentication on Ethernet interfaces.  
  
 Note originally (WinXP SP2 and before) the [Wireless Zero Configuration](/article/winnt-services-wzcsvc.html) service handled the 802.1X authentication for both wireless and wired networks. Now this service handles the 802.1X authentication for wired networks, which requires that the client actively initiates the authentication (EAPOL) instead of just being passive listening. This change was done with the integration of Network Access Protection (NAP), and makes it compliant to the IEEE specifications. More Info [MS KB950725](http://support.microsoft.com/kb/950725 "The Authentication tab is missing in the properties dialog box of the wired network adapter after you install Windows XP SP3").  
  
 More Info [CableGuy - IEEE 802.1X Wired Authentication](http://technet.microsoft.com/en-us/magazine/cc194418.aspx "The Cable Guy  IEEE 802.1X Wired Authentication (February 2008)")
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Vista/Win7: [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (dot3svc)
- WinXP SP3: [svchost.exe -k dot3svc](/article/winnt-services-wrapper.html) (dot3svc)

##### Supports:

- none

##### Depends:

- [Extensible Authentication Protocol](/article/winnt-services-eaphost.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)