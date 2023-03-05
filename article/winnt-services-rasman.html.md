---
title: 'Remote Access Connection Manager'
date: '2000-07-23T16:34:53+02:00'
status: publish
permalink: /article/winnt-services-rasman.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Access Connection Manager service.'
type: post
id: 578
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - dialup-modem
    - VPN
post_format: []
tags:
    - 'dialup-modem,VPN'
---
##### Description:

 Used to connecting, maintaining and disconnecting dial-up and VPN connections from your computer to the Internet or other remote networks.  
  
 With Win2k the VPN module was extended to support Layer 2 Tunnel Protocol (L2TP) connections with [Internet Protocol Security (IPSec)](/article/winnt-services-policyagent.html) for higher security.  
  
 Related [Setting up a Virtual Private Network in Win2k/WinXP](/article/winnt-vpn.html)  
  
 More Info [MS KB234014](http://support.microsoft.com/kb/234014 "HOW TO: Enable PPP Logging in Windows [Q234014]")  
 More Info [MS KB258261](http://support.microsoft.com/kb/258261 "Disabling IPSEC Policy Used with L2TP [Q258261]")  
 More Info [MS KB310109](http://support.microsoft.com/kb/310109 "HOW TO: Disable the Automatic L2TP/IPSec Policy [Q310109]")  
  
##### Recommended State:

- Disabled, if on a simple home network.
- Manual, if using dialup modem for Internet or using VPN to connect to remote networks.

##### Default State:

- Manual

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (RasMan)

##### Supports:

- [Internet Connection Sharing](/article/winnt-services-sharedaccess.html) (Win2k/Vista+)
- [Internet Connection Firewall and Internet Connection Sharing](/article/winxp-services-sharedaccess.html) (WinXP/Win2k3 only)
- [Remote Access Auto Connection Manager](/article/winnt-services-rasauto.html)
- [Routing and Remote Access](/article/winnt-services-remoteaccess.html) (Vista+)

##### Depends:

- [Telephony](/article/winnt-services-tapisrv.html)
- [Secure Socket Tunneling Protocol Service](/article/winnt-services-sstpsvc.html) (Vista SP1+)