---
title: 'Remote Desktop Client'
date: '2002-04-18T21:50:42+02:00'
status: publish
permalink: /article/windows-remote-desktop.html
author: Snakefoot
excerpt: 'Remote Desktop Client can take control of a remote computer running Microsoft Windows.'
type: post
id: 357
category:
    - Utilities
    - Utilities
    - Utilities
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag:
    - remote-desktop
    - terminal-services
post_format: []
tags:
    - 'remote-desktop,terminal-services'
---
Remote Desktop Client (RDC) is installed by default on WinXP, but it will also run on Win9x/WinNT4/Win2k (Is better than the client installed by default on Win2k). Originally the client was called Microsoft Terminal Services client, hence the name MSTSC.

- [RDC 5.1.2600](https://www.microsoft.com/downloads/details.aspx?FamilyID=80111f21-d48d-426e-96c2-08aa2bd23a49)
- [Remote Desktop Web Connection 5.1.2600](http://www.microsoft.com/downloads/details.aspx?FamilyID=469eee3a-45b4-4b40-b695-b678646a728b)
- [Remote Desktop Web Connection 5.2.3790](https://www.microsoft.com/downloads/details.aspx?familyid=E2FF8FB5-97FF-47BC-BACC-92283B52B310)
- [RDC 6.0.2600.0](http://support.microsoft.com/kb/925876)
 
 It allows you to connect to a WinNT4/Win2k/WinXP/Win2k3 installation with [Terminal Services](/article/winnt-services-termservice.html) installed and control it remotely. More Info [MS KB306566](http://support.microsoft.com?id=306566 "HOW TO: Connect Clients to Terminal Services By Using a Terminal Services Client in Windows 2000")  
  
 If using Remote Desktop or VNC to manage many computers, then it might be useful to have a tool to keep track of the different computers:
- Microsoft Remote Desktops snap-in (Tsmmc.msc) is included with Windows 2003 (Also included in the [Windows Server 2003 Administration Tools Pack](/article/winnt-resource-kit.html) and can be used on Windows XP). More Info [MS Technet](http://technet2.microsoft.com/windowsserver/en/library/a94f653f-d109-419f-9b1b-000be51f8dce1033.mspx)
- [Royal TS](http://code4ward.net/cs2/)
- [visionapp Remote Desktop](http://www.visionapp.com/111.0.html)
- [Remote Desktop Manager](http://www.devolutions.net/products/remotedesktopmanager.aspx)
- [mRemote](http://mremote.lostcharacters.net/wiki/) (Opensource)
- [RD Tabs](http://www.avianwaves.com/Tech/Tools/RDTabs/)
 
 Note by default when disconnecting from a remote non-server system, then the user used for login is logged off. To keep the user logged in, then disconnect with this command (Make shortcut in Quick Launch):
> %windir%\\System32\\tscon.exe 0 /dest:console  
>   
>  More Info [MS KB243202](http://support.microsoft.com/kb/243202 "Windows 2000 Terminal Services Session Management Tools [Q243202]")  
>  More Info [MS KB302801](http://support.microsoft.com/kb/302801 "The Use of Tscon.exe Can Leave a Previously-Locked Console Unlocked [Q302801]")

 Note mouse and keyboard movement might seem jerky when doing remote desktop. This can be fixed by setting this registry key on the client-side:
> \[HKEY\_CURENT\_USER \\Software \\Microsoft \\Terminal Server Client\]  
>  Min Send Interval = 10 (Default 100 ms)  
>  Min Send Interval 5 = 10 (Default 120 ms)  
>   
>  More Info [MS KB196460](http://support.microsoft.com/kb/196460 "Improving Mouse Movements in Terminal Server Applications [Q196460]")  
>  More Info [MS KB830209](http://support.microsoft.com/kb/830209 "Mouse Pointer Movement Is Not Smooth If You Use Microsoft Terminal Services Advanced Client 5.1 or Later [Q830209]")  
>  More Info [MS KB831172](http://support.microsoft.com/kb/831172 "Mouse pointer movement is not smooth in Microsoft Remote Desktop Connection [Q831172]")

 Note it is possible create a system console (session 0) connection to a WinXP/Win2k3 computer instead of a terminal services session. Older applications and services will only display their console window and popup message boxes to session 0. Requires an administrator rights on the computer, and only one is allowed to be logged on like this (Default when performing remote desktop to XP):
> mstsc.exe /console  
>   
>  More Info [MS KB278666](http://support.microsoft.com/kb/278666 "Error Message When You Try to Connect to a Terminal Server Computer [Q278666]")  
>  More Info [MS KB311926](http://support.microsoft.com/kb/311926 "You Cannot Use Mstsc.exe with the /CONSOLE Switch to Connect to a Console Session on a Windows 2000 Server-Based Computer [Q311926]")

 Note to start with multi-monitor support:
 > mstsc.exe /span

 Note to see more options:
> mstsc.exe /?  
>   
>  More Info [MS KB304304](http://support.microsoft.com/kb/304304 "Configuring the Remote Desktop Client to Connect to a Specific Port [Q304304]")

 Note it is possible to make a local printer available in a remote session:
1. Click Start -&gt; Run..
   > mstsc.exe
2. Click **Options** in the Remote Desktop Connection dialog box.
3. Click the **Local Resources** tab.
4. Click **Printers** in the Local Devices box.
5. Click **Connect**.
 
 More Info [MS KB243552](http://support.microsoft.com/kb/243552 "How To Manually Add a Redirected Client Printer Using Terminal Services [Q243552]")  
 More Info [MS KB264039](http://support.microsoft.com/kb/264039 "Windows 2000 Terminal Services does not redirect network printers [Q264039]")  
 More Info [MS KB317780](http://support.microsoft.com/kb/317780 "How To Make a Local Printer Available During a Connection to a Remote Desktop in Windows XP Professional [Q317780]")  
  
 Note one can save the settings used for the Remote Desktop Protocol (RDP) connection in a file (Ex. Default.rdp). To save the settings start **mstsc.exe** and in the **Remote Desktop Connection**-dialog select **Options**. More Info [MS KB885187](http://support.microsoft.com/kb/885187 "Remote Desktop Protocol settings in Windows Server 2003 and in Windows XP [Q885187]")  
  
 Related [Remote Desktop in Vista can be slow because of RWIN auto-tuning](/article/vista-tcpip-auto-rwin.html)