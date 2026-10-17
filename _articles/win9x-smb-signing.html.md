---
title: 'Configure SMB signing in Windows 9x'
date: '2003-02-28T21:14:19+01:00'
permalink: /article/win9x-smb-signing.html
author: Snakefoot
excerpt: 'How to increase the security of the Microsoft network by enabling SMB signing.'
type: post
id: 207
categories:
    - windows-95_file-sharing
    - windows-98_file-sharing
    - windows-me_file-sharing
tags:
    - microsoft-network
    - network-performance
    - smb-signing
    - windows-domain
---
It is possible to configure Win98/Me to increase the network security by enabling SMB signing, though enabling it will cause a performance hit because the security requires extra processing.  
  
 Configure client signing in Win98/Me:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\VNetsup\]  
>  EnableSecuritySignature = 0 (Disabled = 0, Enabled = 1)  
>  RequireSecuritySignature= 0 (Disabled = 0, Enabled = 1)

 Note to enable SMB signing on Win95, then one have to install the Directory Services Client, which is found on the Win2k Srv. Install-Cd (X:\\Clients\\Win9x\\Dsclient.exe) along with Winsock2 update and at least <a href="https://www.bing.com/search?q=KB+285189+Q285189" title="Dial-Up Networking 1.4 Upgrade Is Available [Q285189]" rel="nofollow">DUN 1.3+</a>.  
 If doing domain logon check <a href="https://www.bing.com/search?q=KB+249841+Q249841" title="INFO: How Windows 95 and Windows 98 Directory Services Client Uses Active Directory Site Information [Q249841]"), and check that the [DNS Server is properly configured](http://support.microsoft.com/kb/237675 "Setting Up the Domain Name System for Active Directory" rel="nofollow">How the DSClient uses DNS lookup</a> or it can cause slow logon, as it has to timeout before it uses Netbios.  
  
 Related [Description of SMB signing](/article/windows-smb-signing.html)  
  
 More Info <a href="https://www.bing.com/search?q=KB%20230545%20Q230545" rel="nofollow" title="How to Enable SMB Signing in Windows 98 [Q230545]">MS KB230545</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20249841%20Q249841" rel="nofollow" title="INFO: How Windows 95 and Windows 98 Directory Services Client Uses Active Directory Site Information [Q249841]">MS KB249841</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20288358%20Q288358" rel="nofollow" title="How to install the Active Directory client extension [Q288358]">MS KB288358</a> (Download original DsClient.exe)  
 More Info <a href="https://www.bing.com/search?q=KB%20283261%20Q283261" rel="nofollow" title="Version Conflicts with the Directory Service Client Version of Windows 95 and Windows 98 System Files [Q283261]">MS KB283261</a> (Flaw in DsClient.exe)  
 More Info <a href="https://www.bing.com/search?q=KB%20323455%20Q323455" rel="nofollow" title="Availability of the Directory Services Client Update for Windows 98 [Q323455]">MS KB323455</a> (Description of [hotfix](ftp://ftp.catalyst.com/pub/cstools/support/dsclient.exe "Mirror of 5.0.2920.5") for DsClient.exe) (Replaces MS KB323466)  
 More Info <a href="https://www.bing.com/search?q=KB%20555038%20Q555038" rel="nofollow" title="How to enable Windows 98/ME/NT clients to logon to Windows 2003 based Domains [Q555038]">MS KB555038</a> (Using DsClient.exe)  