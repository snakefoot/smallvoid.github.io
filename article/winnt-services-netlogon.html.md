---
title: 'NET Logon'
date: '2000-06-06T15:21:33+02:00'
status: publish
permalink: /article/winnt-services-netlogon.html
author: Snakefoot
excerpt: 'Description and recommended settings for the NET Logon service.'
type: post
id: 563
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - windows-domain
post_format: []
tags:
    - windows-domain
---
##### Description:

 Responsible for network authentication including the following sub-components:  
- Maintains a synced domain directory database between the Primary Domain Controller(PDC) and Backup Domain Controllers(BDC's)
- Handles authentication of respective accounts on the Domain Controllers (DC)
- Handles the process of authentication of domain accounts on networked machines.
 
 Note if the service is disabled then client machines will not be able to discover the domain and will get the error:
> *You must supply a password to make this connection:  
>  Resource: \\\\computername\\[IPC$](/article/winnt-ipc-share.html)*

 More Info [MS KB262916](http://support.microsoft.com/kb/262916 "Unable to Connect to Network Share When Netlogon Service Is Not Started [Q262916]")  
  
##### Recommended State:

- Manual, if on a simple home network.
- Automatic, if connected to a domain.

##### Default State:

- Manual, if in a Workgroup (If started it will stop automatically).
- Automatic, if in a Domain.

##### Process Name:

- [lsass.exe](/article/winnt-services-wrapper.html) (Netlogon)

##### Supports:

- None

##### Depends:

- [Workstation](/article/winnt-services-lanmanworkstation.html)