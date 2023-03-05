---
title: 'Extensible Authentication Protocol'
date: '2007-07-17T02:13:35+02:00'
status: publish
permalink: /article/winnt-services-eaphost.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Extensible Authentication Protocol service.'
type: post
id: 669
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - network-access-protection
    - VPN
    - wifi
    - wireless-network
    - wlan
post_format: []
tags:
    - 'wireless-network,VPN,network-access-protection,wifi,wlan'
---
##### Description:

 The Extensible Authentication Protocol (EAP) service provides network authentication in such scenarios as 802.1x wired and wireless, VPN, and Network Access Protection (NAP). EAP also provides application programming interfaces (APIs) that are used by network access clients, including wireless and VPN clients, during the authentication process. If you disable this service, this computer is prevented from accessing networks that require EAP authentication.  
  
 More Info [Wiki: Extensible Authentication Protocol](http://en.wikipedia.org/wiki/Extensible_Authentication_Protocol)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win8/Win7/Vista: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (EapHost)
- WinXP SP3: [svchost.exe -k eapsvcs](/article/winnt-services-wrapper.html) (EapHost)

##### Supports:

- [Wired AutoConfig](/article/winnt-services-dot3svc.html)
- [WLAN AutoConfig](/article/winnt-services-wlansvc.html) (Win7/Vista only)

##### Depends:

- [CNG Key Isolation](/article/winnt-services-keyiso.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)