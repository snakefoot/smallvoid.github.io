---
title: 'Configure SMB signing in Windows NT'
date: '2002-09-11T21:48:56+02:00'
status: publish
permalink: /article/winnt-smb-signing.html
author: Snakefoot
excerpt: 'How to increase the security of the Microsoft network by enabling SMB signing.'
type: post
id: 212
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - microsoft-network
    - network-performance
    - smb-signing
post_format: []
tags:
    - 'microsoft-network,smb-signing,network-performance'
---
It is possible to configure WinNT SP3+ to increase the network security by enabling SMB signing, though enabling it will cause a performance hit because the security requires extra processing.  
  
 Server Signing in WinNT4/2k/XP :

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanManServer \\Parameters\]  
>  EnableSecuritySignature = 0 (Disabled = 0, Enabled = 1)  
>  RequireSecuritySignature= 0 (Disabled = 0, Enabled = 1)

 Client Signing in WinNT4 SP3+ :  
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Rdr \\Parameters\]  
>  EnableSecuritySignature = 0 (Disabled = 0, Enabled = 1)  
>  RequireSecuritySignature= 0 (Disabled = 0, Enabled = 1)

 Client Signing in Win2k/XP :  
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanManWorkstation \\Parameters\]  
>  EnableSecuritySignature = 0 (Disabled = 0, Enabled = 1)  
>  RequireSecuritySignature= 0 (Disabled = 0, Enabled = 1)

 Note the standard policy for Domain Controllers and Windows 2003 is to use SMB Signing, so if using such device as a fileserver in a trusted network, then one might consider disabling SMB Signing.  
  
 Note one might experience "Delayed Write Failed"-errors when saving/writing to files on network share. This is caused by an error in SMB signing and it can be fixed by updating Win2k and WinXP according to this article. More Info [MS KB814112](http://support.microsoft.com/kb/814112 "Files on network shares open slowly, opens as read-only, or you receive an error message [Q814112]"). Another solution is to set *EnableSecuritySignature = 0*.  
  
 Note to disable SMB Signing for all Domain Controllers in an Active Directory:
1. Open Active Directory Users and Computers
2. In the console tree, right-click Domain Controllers and click Properties
3. Select the Group Policy tab.
4. Click Default Domain Controllers Policy and click Edit
5. Under Security Options right-click Microsoft network server: Digitally sign communications (Always) and select properties
6. Set it to disabled
 
 Related [Description of SMB Signing](/article/windows-smb-signing.html)  
 Related [TCPIP nagle algorithm can slow down network with SMB signing](/article/winnt-nagle-algorithm.html)  
  
 More info [MS KB161372](http://support.microsoft.com/kb/161372 "How to Enable SMB Signing in Windows NT [Q161372]")  
 More info [MS KB199714](http://support.microsoft.com/kb/199714 "Cannot Join Domain Because of SMB Signing [Q199714]")  
 More info [MS KB321169](http://support.microsoft.com/kb/321169 "Slow SMB Performance When You Copy Files from Windows XP to a Windows 2000 Domain Controller [Q321169]")  
 More info [MS KB811497](http://support.microsoft.com/kb/811497 "Error Message When Windows 95 or Windows NT 4.0 Client Logs On to Windows Server 2003 Domain [Q811497]")  
 More info [MS KB814112](http://support.microsoft.com/kb/814112 "Files on Network Shares Open Slowly or Read-Only or You Receive an Error Message [Q814112]")  
 More info [MS KB839499](http://support.microsoft.com/kb/839499 "You cannot open file shares or Group Policy snap-ins when you disable SMB signing for the Workstation or Server service on a domain controller [Q839499]")  
 More info [MS KB887429](http://support.microsoft.com/kb/887429 "Overview of Server Message Block signing [Q887429]")  
  
 Credits [www.jsifaq.com](http://www.jsifaq.com/)