---
title: 'Configure SMB signing in Windows 9x'
date: '2003-02-28T21:14:19+01:00'
status: publish
permalink: /article/win9x-smb-signing.html
author: Snakefoot
excerpt: 'How to increase the security of the Microsoft network by enabling SMB signing.'
type: post
id: 207
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - microsoft-network
    - network-performance
    - smb-signing
    - windows-domain
post_format: []
tags:
    - 'microsoft-network,smb-signing,network-performance,windows-domain'
---
It is possible to configure Win98/Me to increase the network security by enabling SMB signing, though enabling it will cause a performance hit because the security requires extra processing.  
  
 Configure client signing in Win98/Me:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\VNetsup\]  
>  EnableSecuritySignature = 0 (Disabled = 0, Enabled = 1)  
>  RequireSecuritySignature= 0 (Disabled = 0, Enabled = 1)

 Note to enable SMB signing on Win95, then one have to install the Directory Services Client, which is found on the Win2k Srv. Install-Cd (X:\\Clients\\Win9x\\Dsclient.exe) along with Winsock2 update and at least [DUN 1.3+](http://support.microsoft.com/kb/285189 "Dial-Up Networking 1.4 Upgrade Is Available [Q285189]").  
 If doing domain logon check [How the DSClient uses DNS lookup](http://support.microsoft.com/kb/249841 "INFO: How Windows 95 and Windows 98 Directory Services Client Uses Active Directory Site Information [Q249841]"), and check that the [DNS Server is properly configured](http://support.microsoft.com/kb/237675 "Setting Up the Domain Name System for Active Directory") or it can cause slow logon, as it has to timeout before it uses Netbios.  
  
 Related [Description of SMB signing](/article/windows-smb-signing.html)  
  
 More Info [MS KB230545](http://support.microsoft.com/kb/230545 "How to Enable SMB Signing in Windows 98 [Q230545]")  
 More Info [MS KB249841](http://support.microsoft.com/kb/249841 "INFO: How Windows 95 and Windows 98 Directory Services Client Uses Active Directory Site Information [Q249841]")  
 More Info [MS KB288358](http://support.microsoft.com/kb/288358 "How to install the Active Directory client extension [Q288358]") (Download original DsClient.exe)  
 More Info [MS KB283261](http://support.microsoft.com/kb/283261 "Version Conflicts with the Directory Service Client Version of Windows 95 and Windows 98 System Files [Q283261]") (Flaw in DsClient.exe)  
 More Info [MS KB323455](http://support.microsoft.com/kb/323455 "Availability of the Directory Services Client Update for Windows 98 [Q323455]") (Description of [hotfix](ftp://ftp.catalyst.com/pub/cstools/support/dsclient.exe "Mirror of 5.0.2920.5") for DsClient.exe) (Replaces MS KB323466)  
 More Info [MS KB555038](http://support.microsoft.com/kb/555038 "How to enable Windows 98/ME/NT clients to logon to Windows 2003 based Domains [Q555038]") (Using DsClient.exe)  