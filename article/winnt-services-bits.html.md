---
title: 'Background Intelligent Transfer Service (BITS)'
date: '2002-08-06T23:41:41+02:00'
status: publish
permalink: /article/winnt-services-bits.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Background Intelligent Transfer service.'
type: post
id: 525
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - automatic-updates
    - 'Windows Update'
post_format: []
tags:
    - 'windows-update,automatic-updates'
---
##### Description:

 Transfers files in the background using idle network bandwidth, uses the HTTP protocol and supports resuming of broken downloads.  
 BITS can be ordered to a download file, but if the user logs off then it will suspend the file transfer, and resume again when the user logs back on again.  
 BITS starts when a file is added to its download queue, when the queue is empty the service stops again.  
  
 Related [How to configure the bandwidth usage of BITS](/article/winnt-bits-config.html)  
  
 Note if BITS is disabled and an application requests BITS then it will give this error:
> Event ID - 10005  
>  Description - DCOM got error "The service cannot be started, either because it is disabled or because it has no enabled devices associated with it. " attempting to start the service BITS with arguments "" in order to run the server: { 4991D34B-80A1-4291-83B6-3328366B9097 }

 Note if BITS fails to start or operate properly, then stop the service and reset the download queue by deleting the two files listed below. Can also find the files by doing a search for "qmgr" files [MS KB920649](http://support.microsoft.com/kb/920649 "You cannot download new updates from a server that is running Windows Server Update Services"), or if using Windows Vista then use the [BITS Repair Tool](http://support.microsoft.com/kb/940520 "An update is available to fix a Background Intelligent Transfer Service (BITS) crash on a Windows Vista-based computer"):
> %ALLUSERSPROFILE%\\Application Data\\Microsoft\\Network\\Downloader\\**qmgr0.dat**  
>  %ALLUSERSPROFILE%\\Application Data\\Microsoft\\Network\\Downloader\\**qmgr1.dat**

 More Info [MS KB326460](http://support.microsoft.com/kb/326460 ""Service-Specific Error Code -2147944102" Error Message If You Try to Start the Background Intelligent Transfer Service (BITS) Service [Q326460]") (Previous MS KB326607)  
 More Info [BITSAdmin Tool](http://msdn.microsoft.com/library/en-us/bits/bits/bitsadmin_tool.asp) [Examples](http://msdn.microsoft.com/library/en-us/bits/bits/bitsadmin_examples.asp)  
  
##### Recommended State:

- Manual, if using [Windows Update](http://windowsupdate.microsoft.com/), [Automatic Updates](/article/winnt-services-wuauserv.html) or want your programs like Windows, MSN Explorer etc. updated in the background.
- Disabled, if you want manually to control when Windows and your programs are updated.

##### Default State:

- Win8 - Automatic (Delayed Start)
- Win7 - Manual
- Vista - Automatic (Delayed Start)
- WinXP/2K3: Manual
- Win2k SP3+: Automatic

##### Process Name:

- WinXP Pro/2k3/Vista/Win7/Win8: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (BITS)
- Win2k: [svchost.exe -k BITSgroup](/article/winnt-services-wrapper.html) (BITS)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [COM+ Event System](/article/winnt-services-eventsystem.html) (Vista+)
- [Workstation](/article/winnt-services-lanmanworkstation.html) (Win2k SP3+ only)
- [System Event Notification](/article/winnt-services-sens.html) (Win2k SP3+ only)
- [Windows Management Instrumentation Driver Extensions](/article/winnt-services-wmi.html) (Win2k SP3+ only)