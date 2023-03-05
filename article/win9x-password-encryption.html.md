---
title: 'Configure password encryption level in Windows 9x'
date: '2003-09-19T21:28:42+02:00'
status: publish
permalink: /article/win9x-password-encryption.html
author: Snakefoot
excerpt: 'How to configure the password encryption level for better security.'
type: post
id: 210
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - encryption
    - password
    - windows-domain
post_format: []
tags:
    - 'encryption,password,windows-domain'
---
A low Password Encryption level is used by default to give a higher level of compatibility, but makes it easy for an intruder to use a network sniffer for discovering other user's username and password.  
  
 Note before Win95/Win98/WinMe can be configured to use a higher level of encryption, then one have to install the Directory Services Client, which is found on the Win2k Install-Cd (X:\\Clients\\Win9x\\Dsclient.exe), and Win95 also requires that Winsock2 update and at least [DUN 1.3+](http://support.microsoft.com/kb/285189 "Dial-Up Networking 1.4 Upgrade Is Available [Q285189]") is installed.  
 If doing domain logon learn [How the DSClient uses DNS lookup](http://support.microsoft.com/kb/249841 "INFO: How Windows 95 and Windows 98 Directory Services Client Uses Active Directory Site Information [Q249841]"), and check that the [DNS Server is properly configured](http://support.microsoft.com/kb/237675 "Setting Up the Domain Name System for Active Directory [Q237675]") or it can cause slow logon, as it has to timeout before it uses Netbios.  
  
 Configure the Lan Manager Compatibility level in Challenge/Response:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\LSA\]  
>  LMCompatibility = 3 (Default 0)  
>   
>  Level 0 = Client uses LM and NTLM  
>  Level 3 = Client only uses NTML2  
>   
>  More Info [MS KB239869](http://support.microsoft.com/kb/239869 "How to enable NTLM 2 authentication [Q239869]")

 Configure the LanManager Security Support Provider (SSP):
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\control \\LSA \\MSV1\_0\]  
 >  NtlmMinClientSec = 0x20080030 (Default 0)  
 >   
 >  0x20080030 = 128 Bit, NTLM2, Message Confidentiality, Message Integrity  
 >   
 >  Note to reach 128 bit encryption one have to install the Internet Explorer with 128 encryption before installing the Directoy Services Client.  
 >   
 >  More Info [MS KB239869](http://support.microsoft.com/kb/239869 "How to enable NTLM 2 authentication [Q239869]")

 The LanManager can be configured not to require Challenge/Response(CHAP), but also allow Password Authentication Protocol(PAP):
 
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\VNETSUP\]  
 >  EnablePlainTextPassword = 1 (Default = 0 and the most secure)  
 >   
 >  More Info [MS KB185612](http://support.microsoft.com/kb/185612 "Invalid Password Error Message After You Upgrade to Windows 98 [Q185612]")  
 >  More Info [MS KB187228](http://support.microsoft.com/kb/187228 "Unable to Connect to a Samba Server with Windows 98 [Q187228]")

 More Info [MS KB249841](http://support.microsoft.com/kb/249841 "INFO: How Windows 95 and Windows 98 Directory Services Client Uses Active Directory Site Information [Q249841]")  
 More Info [MS KB288358](http://support.microsoft.com/kb/288358 "How to install the Active Directory client extension") (Download original DsClient.exe)  
 More Info [MS KB283261](http://support.microsoft.com/kb/283261 "Version Conflicts with the Directory Service Client Version of Windows 95 and Windows 98 System Files [Q283261]") (Flaw in DsClient.exe)  
 More Info [MS KB323455](http://support.microsoft.com/kb/323455 "Availability of the Directory Services Client Update for Windows 98 [Q323455]") (Description of [Hotfix](ftp://ftp.catalyst.com/pub/cstools/support/dsclient.exe "Mirror of 5.0.2920.5") for DsClient.exe) (Replaces MS KB323466)  
 More Info [MS KB555038](http://support.microsoft.com/kb/555038 "How to enable Windows 98/ME/NT clients to logon to Windows 2003 based Domains [Q555038]") (Using DsClient.exe)  
  
 Related [Description of password encryption level over network](/article/windows-password-encryption.html)