---
title: 'Terminal Services'
date: '2000-07-23T19:37:33+02:00'
permalink: /article/winnt-services-termservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Terminal Services service.'
type: post
id: 605
categories:
    - windows-2000_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
tags:
    - fast-user-switching
    - remote-assistance
    - remote-desktop
    - terminal-services
---
##### Description:

 Terminal Services allows multiple users to be connected interactively to the computer as they were logged on locally.  
 Terminal Services also provides the feature of displaying the desktops and applications to remote computers.  
  
 The terminal server uses by default port 3389 to listen for incoming remote control connections. This can be configured with this registry setting:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\TerminalServer \\WinStations \\RDP-Tcp\]  
>  PortNumber = 3389  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20187623%20Q187623" rel="nofollow" title="How to Change Terminal Server's Listening Port [Q187623]">MS KB187623</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20306759%20Q306759" rel="nofollow" title="How to Change the Listening Port for Remote Desktop [Q306759]">MS KB306759</a>

 Note when connecting to Windows 2000 with Remote Desktop then it will only display 256 colors. To get around this limitation then one has to upgrade to Windows XP/2003. More Info <a href="https://www.bing.com/search?q=KB%20273725%20Q273725" rel="nofollow" title="Cannot Increase the Screen Resolution to Greater Than 256 Colors in Terminal Services [Q273725]">MS KB273725</a>  
  
 Note when connecting to Windows XP Pro with Remote Desktop then it will only allow to receive a single session. If using Windows XP Home then it is only possible to receive [Remote Assistance](/article/winnt-remote-assistance.html).  
  
 Note during the BETA testing of WinXP SP2 it became possible to have a locally and remotely logged on user at the same time. It required that it was two different accounts and [Fast User Switching](/article/winnt-services-fus.html) was turned on along with the [Welcome Screen](/article/winxp-welcome-screen.html). The ability was removed just before SP2 was released, but it worked with Build 2055 of termsrv.dll when setting these DWORD registry keys:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Terminal Server \\Licensing Core\]  
>  EnableConcurrentSessions = 1  
>  MaxInstanceCount = 2

 Related [Remote Desktop Client](/article/windows-remote-desktop.html)  
  
 More Info [MS Terminal Services FAQ (Win2k)](http://www.microsoft.com/windows2000/community/centers/terminal/terminal_faq.mspx "Windows Server Community - Terminal Services FAQ")  
 More Info <a href="https://www.bing.com/search?q=KB%20186566%20Q186566" rel="nofollow" title="Connection Configuration in Terminal Server [Q186566]">MS KB186566</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20186607%20Q186607" rel="nofollow" title="Understanding the Remote Desktop Protocol (RDP) [Q186607]">MS KB186607</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20278502%20Q278502" rel="nofollow" title="HOW TO: Connect to Terminal Services with Color Resolution That Is Greater Than 256 in Windows XP [Q278502]">MS KB278502</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20306561%20Q306561" rel="nofollow" title="HOW TO: Secure Communication Between a Client and Server with Terminal Services [Q306561]">MS KB306561</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20323353%20Q323353" rel="nofollow" title="HOW TO: Connect to Terminal Services with a Color Resolution of Greater Than 256 Colors in the Windows Server 2003 Family [Q323353]">MS KB323353</a>  
  
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