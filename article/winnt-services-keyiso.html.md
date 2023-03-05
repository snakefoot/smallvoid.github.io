---
title: 'CNG Key Isolation'
date: '2007-07-17T02:12:40+02:00'
status: publish
permalink: /article/winnt-services-keyiso.html
author: Snakefoot
excerpt: 'Description and recommended settings for the CNG Key Isolation service.'
type: post
id: 663
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - wifi
    - wireless-network
    - wlan
post_format: []
tags:
    - 'wireless-network,wlan,wifi'
---
##### Description:

 The CNG (Cryptographic Next Generation) key isolation service is hosted in the LSA process. The service provides key process isolation to private keys and associated cryptographic operations as required by the Common Criteria. The service stores and uses long-lived keys in a secure process complying with Common Criteria requirements.  
  
 This service is required for wireless networks (WLAN).  
  
 More Info [MSDN - CNG Features](http://msdn.microsoft.com/en-us/library/bb204775.aspx)  
 More Info [MSDN - Key Storage and Retrieval](http://msdn2.microsoft.com/en-us/library/bb204778.aspx)  
 More Info [Wiki - Common Criteria](http://en.wikipedia.org/wiki/Common_Criteria)  
##### Recommended state:

- Manual

##### Default State:

- Win8: Manual (Trigger Start)
- Win7/Vista: Manual

##### Proces name:

- [lsass.exe](/article/winnt-services-wrapper.html) (KeyIso)

##### Supports:

- [Extensible Authentication Protocol](/article/winnt-services-eaphost.html)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)