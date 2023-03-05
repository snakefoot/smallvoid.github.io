---
title: 'IKE and AuthIP IPsec Keying Modules'
date: '2007-07-17T02:13:59+02:00'
status: publish
permalink: /article/winnt-services-ikeext.html
author: Snakefoot
excerpt: 'Description and recommended settings for the IKE and AuthIP IPsec Keying Modules service.'
type: post
id: 674
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - ipsec
    - VPN
post_format: []
tags:
    - 'VPN,ipsec'
---
##### Description:

 The IKEEXT service hosts the Internet Key Exchange (IKE) and Authenticated Internet Protocol (AuthIP) keying modules. These keying modules are used for authentication and key exchange in Internet Protocol security (IPsec). Stopping or disabling the IKEEXT service will disable IKE and AuthIP key exchange with peer computers. IPsec is typically configured to use IKE or AuthIP; therefore, stopping or disabling the IKEEXT service might result in an IPsec failure and might compromise the security of the system. It is strongly recommended that you have the IKEEXT service running.
 
##### Recommended state:

- Manual

##### Default State:

- Win8 - Manual (Trigger Start - FIREWALL PORT EVENT)
- Win7 - Manual
- Vista - Automatic

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (IKEEXT)

##### Supports:

- none

##### Depends:

- [Base Filtering Engine](/article/winnt-services-bfe.html)