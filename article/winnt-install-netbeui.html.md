---
title: 'Install the deprecated NetBEUI protocol'
date: '2001-11-09T00:34:13+01:00'
status: publish
permalink: /article/winnt-install-netbeui.html
author: Snakefoot
excerpt: 'How to install the NetBEUI protocol eventhough no longer a supported network protocol.'
type: post
id: 432
category:
    - Network
    - Network
tag:
    - netbeui
    - network-protocol
post_format: []
tags:
    - 'network-protocol,netbeui'
---
Microsoft has stopped the support for the NetBEUI (NetBIOS Extended User Interface) protocol with the release of Windows XP / 2003. Though you can still find the needed files (Nbf.sys &amp; Netnbf.inf) on your WinXP CD-ROM (DriveLetter-X):

> X:\\Valueadd\\Msft\\Net\\Netbeui

 To install the protocol on WinXP/Win2k3 from the WinXP Install CD:
1. Copy the file **Nbf.sys** to the folder **%Systemroot%\\System32**
2. Copy the file **Netnbf.inf** to the folder **%Systemroot%\\Inf** (Hidden folder)
3. Click **Start**, Click **Control Panel** and double-click **Network Connections**
4. Right click the connection, where NetBEUI should be used, and then click **Properties**
5. On the **General** tab, click **Install**
6. Click **Protocol**, and click **Add**
7. Select the **NetBEUI Protocol** and then click **Ok**
 
 Note some users has trouble with occasional "Network not available" when using the NetBEUI supplied with WinXP. They had better success using NETNBF.INF and NBF.SYS from a Win2k CD-ROM (Maybe the fact that they reinstalled the protocol is the clue).  
  
 More Info [MS KB301041](http://support.microsoft.com/kb/301041 "HOW TO: Install NetBEUI on Windows XP [Q301041]")  
 More Info [MS Technet](http://www.microsoft.com/technet/archive/winntas/support/sur_nbf.mspx) - Using NetBEUI with Windows NT  
 More Info [MS Technet](http://www.microsoft.com/technet/prodtechnol/windows2000serv/reskit/intwork/inde_nbf_hlpj.mspx "NetBIOS Extended User Interface (NetBEUI) in Windows 2000") - Overview of Windows 2000 NetBEUI  