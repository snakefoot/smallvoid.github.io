---
title: 'Encrypting File System (EFS)'
date: '2009-09-18T18:59:30+02:00'
permalink: /article/winnt-services-efs.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Encrypting File System (EFS) service.'
type: post
id: 800
categories:
    - windows-7-win7_services-guide
    - windows-8-win8_services-guide
tags:
    - encryption
    - file-system
    - ntfs
---
##### Description:

 Provides the core file encryption technology used to store encrypted files on NTFS file system volumes. If this service is stopped or disabled, applications will be unable to access encrypted files.
 
##### Recommended state:

- Manual

##### Default State:

- Win8: Manual (Trigger Start)
- Win7: Manual

##### Proces name:

- [lsass.exe](/article/winnt-services-wrapper.html) (EFS)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)