---
title: 'Certificate Propagation'
date: '2007-07-17T02:12:27+02:00'
status: publish
permalink: /article/winnt-services-certpropsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Certificate Propagation service.'
type: post
id: 662
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Copies user certificates and root certificates from smart cards into the current user's certificate store, detects when a smart card is inserted into a smart card reader, and, if needed, installs the smart card Plug and Play minidriver.  
  
 Allows Smart Cards to supply trustworthy root certificates which can be used to perform Windows login.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (CertPropSvc)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)