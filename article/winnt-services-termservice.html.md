---
title: 'Terminal Services'
date: '2000-07-23T19:37:33+02:00'
status: publish
permalink: /article/winnt-services-termservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Terminal Services service.'
type: post
id: 605
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - fast-user-switching
    - remote-assistance
    - remote-desktop
    - terminal-services
post_format: []
tags:
    - 'remote-desktop,remote-assistance,fast-user-switching,terminal-services'
---
##### Description:

 Terminal Services allows multiple users to be connected interactively to the computer as they were logged on locally.  
 Terminal Services also provides the feature of displaying the desktops and applications to remote computers.  
  
 The terminal server uses by default port 3389 to listen for incoming remote control connections. This can be configured with this registry setting:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\TerminalServer \\WinStations \\RDP-Tcp\]  
>  PortNumber = 3389  
>   
>  More Info [MS KB187623](http://support.microsoft.com/kb/187623 "How to Change Terminal Server's Listening Port [Q187623]")  
>  More Info [MS KB306759](http://support.microsoft.com/kb/306759 "How to Change the Listening Port for Remote Desktop [Q306759]")

 Note when connecting to Windows 2000 with Remote Desktop then it will only display 256 colors. To get around this limitation then one has to upgrade to Windows XP/2003. More Info [MS KB273725](http://support.microsoft.com/kb/273725 "Cannot Increase the Screen Resolution to Greater Than 256 Colors in Terminal Services [Q273725]")  
  
 Note when connecting to Windows XP Pro with Remote Desktop then it will only allow to receive a single session. If using Windows XP Home then it is only possible to receive [Remote Assistance](/article/winnt-remote-assistance.html).  
  
 Note during the BETA testing of WinXP SP2 it became possible to have a locally and remotely logged on user at the same time. It required that it was two different accounts and [Fast User Switching](/article/winnt-services-fus.html) was turned on along with the [Welcome Screen](/article/winxp-welcome-screen.html). The ability was removed just before SP2 was released, but it worked with Build 2055 of termsrv.dll when setting these DWORD registry keys:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Terminal Server \\Licensing Core\]  
>  EnableConcurrentSessions = 1  
>  MaxInstanceCount = 2

 Related [Remote Desktop Client](/article/windows-remote-desktop.html)  
  
 More Info [MS Terminal Services FAQ (Win2k)](http://www.microsoft.com/windows2000/community/centers/terminal/terminal_faq.mspx "Windows Server Community - Terminal Services FAQ")  
 More Info [MS KB186566](http://support.microsoft.com/kb/186566 "Connection Configuration in Terminal Server [Q186566]")  
 More Info [MS KB186607](http://support.microsoft.com/kb/186607 "Understanding the Remote Desktop Protocol (RDP) [Q186607]")  
 More Info [MS KB278502](http://support.microsoft.com/kb/278502 "HOW TO: Connect to Terminal Services with Color Resolution That Is Greater Than 256 in Windows XP [Q278502]")  
 More Info [MS KB306561](http://support.microsoft.com/kb/306561 "HOW TO: Secure Communication Between a Client and Server with Terminal Services [Q306561]")  
 More Info [MS KB323353](http://support.microsoft.com/kb/323353 "HOW TO: Connect to Terminal Services with a Color Resolution of Greater Than 256 Colors in the Windows Server 2003 Family [Q323353]")  
  
##### Recommended State:

- Disabled, for security measures.
- Manual, if using [Remote Desktop](/article/windows-remote-desktop.html)(Remote Administration), [Remote Assistance](/article/winnt-remote-assistance.html), [Fast User Switching](/article/winnt-services-fus.html).

##### Default State:

- Manual.
- Vista: Automatic.

##### Process Name:

- Win2k: termsrv.exe (TermService)
- WinXP: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (TermService)
- WinXP SP2: [svchost.exe -k DcomLaunch](/article/winnt-services-wrapper.html) (TermService)
- Win2k3: [svchost.exe -k termsvcs](/article/winnt-services-wrapper.html) (TermService)
- Vista: [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (TermService)

##### Supports:

- [Fast User Switching](/article/winnt-services-fus.html) (WinXP only)
- [Terminal Services UserMode Port Redirector](/article/winnt-services-umrdpservice.html) (Vista+)
- [Windows Media Center Extender Service](/article/winnt-services-mcx2svc.html) (Vista+)

##### Depends:

- None