---
title: 'Windows Time'
date: '2000-07-06T23:21:37+02:00'
permalink: /article/winnt-services-w32time.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Time service.'
type: post
id: 622
categories:
    - windows-2000_services
    - windows-nt4_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
tags:
    - time-server
---
##### Description:

 Makes it possible to synchronize the computer clock with another system using the Network Time Protocol (NPT) on TCPIP port 123 (UDP).  
  
 Note in WinXP it will automatically try to synchronize with an Internet Time Server. To configure this synchronization double click the clock on the taskbar and select the Internet Time-tab.
 > net time /?  
>   
>  Note NET TIME uses the [IPC$](/article/winnt-ipc-share.html) to synchronize time, thus the remote machine need to have the Server service (File and Printer Sharing) activated.

 To restore the Windows Time Service if it has been broken, run these commands:
> net stop W32Time  
>  w32tm /unregister  
>  w32tm /register  
>  net start W32Time

 More Info <a href="https://www.bing.com/search?q=KB%20120944%20Q120944" rel="nofollow" title="Using NET TIME for all Workstations and Servers [Q120944]">MS KB120944</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20216734%20Q216734" rel="nofollow" title="How to Configure an Authoritative Time Server in Windows [Q216734]">MS KB216734</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20223184%20Q223184" rel="nofollow" title="Registry Entries for the W32Time Service [Q223184]">MS KB223184</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20224799%20Q224799" rel="nofollow" title="Basic Operation of the Windows Time Service [Q224799]">MS KB224799</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20232209%20Q232209" rel="nofollow" title="Win32 Time Service Informational, Warning, and Error Messages [Q232209]">MS KB232209</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20258059%20Q258059" rel="nofollow" title="How to Synchronize the Time on a Windows 2000-Based Computer in a Windows NT 4.0 Domain [Q258059]">MS KB258059</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20307897%20Q307897" rel="nofollow" title="HOW TO: Synchronize the Time with the Windows Time Service in Windows XP [Q307897]">MS KB307897</a>  
  
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