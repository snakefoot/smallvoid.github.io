---
title: 'WLAN AutoConfig'
date: '2007-07-17T02:18:37+02:00'
status: publish
permalink: /article/winnt-services-wlansvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the WLAN AutoConfig service.'
type: post
id: 730
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - wifi
    - wireless-network
    - wlan
post_format: []
tags:
    - 'wireless-network,wifi,wlan'
---
##### Description:

 The WLANSVC service provides the logic required to configure, discover, connect to, and disconnect from a wireless local area network (WLAN) as defined by IEEE 802.11 standards. It also contains the logic to turn your computer into a software access point so that other devices or computers can connect to your computer wirelessly using a WLAN adapter that can support this. Stopping or disabling the WLANSVC service will make all WLAN adapters on your computer inaccessible from the Windows networking UI. It is strongly recommended that you have the WLANSVC service running if your computer has a WLAN adapter.  
  
 Note Windows 2008 doesn't include support for Wireless Networks by default. The feature "Wireless LAN Service" must be installed manually through the Service Manager (in Administrator Tools).  
  
 More Info [Wireless LAN Service Overview](http://technet.microsoft.com/en-us/library/cc730957.aspx)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (Wlansvc)

##### Supports:

- none

##### Depends:

- [Extensible Authentication Protocol](/article/winnt-services-eaphost.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)