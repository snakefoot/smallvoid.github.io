---
title: 'Microsoft iSCSI Initiator Service'
date: '2007-07-17T02:14:28+02:00'
status: publish
permalink: /article/winnt-services-msiscsi.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Microsoft iSCSI Initiator Service.'
type: post
id: 680
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - iscsi
post_format: []
tags:
    - iscsi
---
##### Description:

 Manages Internet SCSI (iSCSI) sessions from this computer to remote iSCSI target devices. If this service is stopped, this computer will not be able to login or access iSCSI targets.  
  
 More Info [Microsoft Storage Technologies - iSCSI](http://www.microsoft.com/windowsserver2003/technologies/storage/iscsi/default.mspx)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (MSiSCSI)

##### Supports:

- none

##### Depends:

- none