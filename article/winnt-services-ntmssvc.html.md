---
title: 'Removable Storage Manager (RSM)'
date: '2000-07-23T15:40:03+02:00'
status: publish
permalink: /article/winnt-services-ntmssvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Removable Storage Manager service.'
type: post
id: 585
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Manages removable media, drives, and libraries.  
  
 This is not needed for CD\\DVD\\Floppy drives, but is intended for Tape drives.  
  
 Note if having set this service to Manual or Disabled and starting [Ntbackup](/article/winnt-ntbackup.html), then a warning will popup about "Removable storage not running". This is only means that Ntbackup will not be able to access any tape-drives for backup/restore of files.  
  
 Note if the Removable Storage database have become corrupted, then this service will fail to respond. This will cause applications like [Ntbackup](/article/winnt-ntbackup.html) to hang and not load properly. To clear the database, make a backup of the contents in this folder and then empty the folder:
> C:\\Windows\\System32\\Ntmsdata  
>   
>  More Info [MS KB235032](http://support.microsoft.com/kb/235032 "Problems with a Damaged Removable Storage Manager Database [Q235032]")  
>  More Info [MS KB248800](http://support.microsoft.com/kb/248800 "Removable Storage Manager Reports Automatic Library Configuration Error Messages [Q248800]")  
>  More Info [MS KB316500](http://support.microsoft.com/kb/316500 "The Removable Storage Service Hangs on Startup [Q316500]")

 More Info [MS KB226932](http://support.microsoft.com/kb/226932 "Windows 2000 Removable Storage Manager Performs Tasks Sequentially [Q226932]")  
 More Info [MS KB235032](http://support.microsoft.com/kb/235032 "Event ID 129 for Removable Storage Manager After Reboot [Q235032]")  
 More Info [MS KB240856](http://support.microsoft.com/kb/240856 "Removable Storage Manager Terms and Definitions [Q240856]")  
 More Info [MS KB250468](http://support.microsoft.com/kb/250468 "How Removable Storage Manager and Programs Recognize Media [Q250468]")  
  
##### Recommended State:

- Manual, if not using tape drives.

##### Default State:

- Win2k Srv.: Automatic
- WinXP: Manual
- Win2k3: Manual

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (NtmsSvc)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)