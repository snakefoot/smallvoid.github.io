---
title: 'Credential Manager Service'
date: '2010-03-02T00:57:00+01:00'
status: publish
permalink: /article/winnt-services-vaultsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Credential Manager Service (VaultSvc).'
type: post
id: 827
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Provides secure storage and retrieval of credentials to users, applications and security service packages.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [lsass.exe](/article/winnt-services-wrapper.html) (VaultSvc)

##### Supports:

- [Windows Biometric Service](/article/winnt-services-wbiosrvc.html)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)