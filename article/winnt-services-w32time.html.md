---
title: 'Windows Time'
date: '2000-07-06T23:21:37+02:00'
status: publish
permalink: /article/winnt-services-w32time.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Time service.'
type: post
id: 622
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - time-server
post_format: []
tags:
    - time-server
---
##### Description:

 Makes it possible to synchronize the computer clock with another system using the Network Time Protocol (NPT) on TCPIP port 123 (UDP).  
  
 Note in WinXP it will automatically try to synchronize with an Internet Time Server. To configure this synchronization double click the clock on the taskbar and select the Internet Time-tab. > net time /?  
>   
>  Note NET TIME uses the [IPC$](/article/winnt-ipc-share.html) to synchronize time, thus the remote machine need to have the Server service (File and Printer Sharing) activated.

 To restore the Windows Time Service if it has been broken, run these commands:
> net stop W32Time  
>  w32tm /unregister  
>  w32tm /register  
>  net start W32Time

 More Info [MS KB120944](http://support.microsoft.com/kb/120944 "Using NET TIME for all Workstations and Servers [Q120944]")  
 More Info [MS KB216734](http://support.microsoft.com/kb/216734 "How to Configure an Authoritative Time Server in Windows [Q216734]")  
 More Info [MS KB223184](http://support.microsoft.com/kb/223184 "Registry Entries for the W32Time Service [Q223184]")  
 More Info [MS KB224799](http://support.microsoft.com/kb/224799 "Basic Operation of the Windows Time Service [Q224799]")  
 More Info [MS KB232209](http://support.microsoft.com/kb/232209 "Win32 Time Service Informational, Warning, and Error Messages [Q232209]")  
 More Info [MS KB258059](http://support.microsoft.com/kb/258059 "How to Synchronize the Time on a Windows 2000-Based Computer in a Windows NT 4.0 Domain [Q258059]")  
 More Info [MS KB307897](http://support.microsoft.com/kb/307897 "HOW TO: Synchronize the Time with the Windows Time Service in Windows XP [Q307897]")  
  
##### Recommended State:

- Automatic, if doing domain logon where the client-time must not be more than 5 mins off.
- Disabled, if not needing to be that timely.

##### Default State:

- WinNT4/2k: Manual.
- WinXP/Win2k3/Vista: Automatic.
- Win7: Manual.

##### Process Name:

- WinNT4/2k: [services.exe](/article/winnt-services-wrapper.html) (W32Time)
- WinXP/Win2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (W32Time)
- Vista/Win7: [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (W32Time)

##### Supports:

- None

##### Depends:

- None