---
title: 'Remote Desktop Client'
date: '2002-04-18T21:50:42+02:00'
permalink: /article/windows-remote-desktop.html
author: Snakefoot
excerpt: 'Remote Desktop Client can take control of a remote computer running Microsoft Windows.'
type: post
id: 357
categories:
    - windows-2000_utilities
    - windows-2003_utilities
    - windows-95_utilities
    - windows-98_utilities
    - windows-me_utilities
    - windows-nt4_utilities
    - windows-xp_utilities
tags:
    - remote-desktop
    - terminal-services
---
Remote Desktop Client (RDC) is installed by default on WinXP, but it will also run on Win9x/WinNT4/Win2k (Is better than the client installed by default on Win2k). Originally the client was called Microsoft Terminal Services client, hence the name MSTSC.

- [RDC 5.1.2600](https://www.microsoft.com/downloads/details.aspx?FamilyID=80111f21-d48d-426e-96c2-08aa2bd23a49)
- [Remote Desktop Web Connection 5.1.2600](http://www.microsoft.com/downloads/details.aspx?FamilyID=469eee3a-45b4-4b40-b695-b678646a728b)
- [Remote Desktop Web Connection 5.2.3790](https://www.microsoft.com/downloads/details.aspx?familyid=E2FF8FB5-97FF-47BC-BACC-92283B52B310)
- <a href="https://www.bing.com/search?q=KB+925876+Q925876" rel="nofollow">RDC 6.0.2600.0</a>
 
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
>  More Info <a href="https://www.bing.com/search?q=KB%20243202%20Q243202" rel="nofollow" title="Windows 2000 Terminal Services Session Management Tools [Q243202]">MS KB243202</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20302801%20Q302801" rel="nofollow" title="The Use of Tscon.exe Can Leave a Previously-Locked Console Unlocked [Q302801]">MS KB302801</a>

 Note mouse and keyboard movement might seem jerky when doing remote desktop. This can be fixed by setting this registry key on the client-side:
> \[HKEY\_CURENT\_USER \\Software \\Microsoft \\Terminal Server Client\]  
>  Min Send Interval = 10 (Default 100 ms)  
>  Min Send Interval 5 = 10 (Default 120 ms)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20196460%20Q196460" rel="nofollow" title="Improving Mouse Movements in Terminal Server Applications [Q196460]">MS KB196460</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20830209%20Q830209" rel="nofollow" title="Mouse Pointer Movement Is Not Smooth If You Use Microsoft Terminal Services Advanced Client 5.1 or Later [Q830209]">MS KB830209</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20831172%20Q831172" rel="nofollow" title="Mouse pointer movement is not smooth in Microsoft Remote Desktop Connection [Q831172]">MS KB831172</a>

 Note it is possible create a system console (session 0) connection to a WinXP/Win2k3 computer instead of a terminal services session. Older applications and services will only display their console window and popup message boxes to session 0. Requires an administrator rights on the computer, and only one is allowed to be logged on like this (Default when performing remote desktop to XP):
> mstsc.exe /console  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20278666%20Q278666" rel="nofollow" title="Error Message When You Try to Connect to a Terminal Server Computer [Q278666]">MS KB278666</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20311926%20Q311926" rel="nofollow" title="You Cannot Use Mstsc.exe with the /CONSOLE Switch to Connect to a Console Session on a Windows 2000 Server-Based Computer [Q311926]">MS KB311926</a>

 Note to start with multi-monitor support:
 > mstsc.exe /span

 Note to see more options:
> mstsc.exe /?  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20304304%20Q304304" rel="nofollow" title="Configuring the Remote Desktop Client to Connect to a Specific Port [Q304304]">MS KB304304</a>

 Note it is possible to make a local printer available in a remote session:
1. Click Start -&gt; Run..
   > mstsc.exe
2. Click **Options** in the Remote Desktop Connection dialog box.
3. Click the **Local Resources** tab.
4. Click **Printers** in the Local Devices box.
5. Click **Connect**.
 
 More Info <a href="https://www.bing.com/search?q=KB%20243552%20Q243552" rel="nofollow" title="How To Manually Add a Redirected Client Printer Using Terminal Services [Q243552]">MS KB243552</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20264039%20Q264039" rel="nofollow" title="Windows 2000 Terminal Services does not redirect network printers [Q264039]">MS KB264039</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20317780%20Q317780" rel="nofollow" title="How To Make a Local Printer Available During a Connection to a Remote Desktop in Windows XP Professional [Q317780]">MS KB317780</a>  
  
 Note one can save the settings used for the Remote Desktop Protocol (RDP) connection in a file (Ex. Default.rdp). To save the settings start **mstsc.exe** and in the **Remote Desktop Connection**-dialog select **Options**. More Info <a href="https://www.bing.com/search?q=KB%20885187%20Q885187" rel="nofollow" title="Remote Desktop Protocol settings in Windows Server 2003 and in Windows XP [Q885187]">MS KB885187</a>  
  
 Related [Remote Desktop in Vista can be slow because of RWIN auto-tuning](/article/vista-tcpip-auto-rwin.html)