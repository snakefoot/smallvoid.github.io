---
title: 'Removable Storage Manager (RSM)'
date: '2000-07-23T15:40:03+02:00'
permalink: /article/winnt-services-ntmssvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Removable Storage Manager service.'
type: post
id: 585
categories:
    - windows-2000_services
    - windows-2003_services
    - windows-xp_services
tags: []
---
##### Description:

 Manages removable media, drives, and libraries.  
  
 This is not needed for CD\\DVD\\Floppy drives, but is intended for Tape drives.  
  
 Note if having set this service to Manual or Disabled and starting [Ntbackup](/article/winnt-ntbackup.html), then a warning will popup about "Removable storage not running". This is only means that Ntbackup will not be able to access any tape-drives for backup/restore of files.  
  
 Note if the Removable Storage database have become corrupted, then this service will fail to respond. This will cause applications like [Ntbackup](/article/winnt-ntbackup.html) to hang and not load properly. To clear the database, make a backup of the contents in this folder and then empty the folder:
> C:\\Windows\\System32\\Ntmsdata  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+235032+Q235032" rel="nofollow" title="Problems with a Damaged Removable Storage Manager Database [Q235032]">MS KB235032</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+248800+Q248800" rel="nofollow" title="Removable Storage Manager Reports Automatic Library Configuration Error Messages [Q248800]">MS KB248800</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+316500+Q316500" rel="nofollow" title="The Removable Storage Service Hangs on Startup [Q316500]">MS KB316500</a>

 More Info <a href="https://www.bing.com/search?q=KB+226932+Q226932" rel="nofollow" title="Windows 2000 Removable Storage Manager Performs Tasks Sequentially [Q226932]">MS KB226932</a>  
 More Info <a href="https://www.bing.com/search?q=KB+235032+Q235032" rel="nofollow" title="Event ID 129 for Removable Storage Manager After Reboot [Q235032]">MS KB235032</a>  
 More Info <a href="https://www.bing.com/search?q=KB+240856+Q240856" rel="nofollow" title="Removable Storage Manager Terms and Definitions [Q240856]">MS KB240856</a>  
 More Info <a href="https://www.bing.com/search?q=KB+250468+Q250468" rel="nofollow" title="How Removable Storage Manager and Programs Recognize Media [Q250468]">MS KB250468</a>  
  
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