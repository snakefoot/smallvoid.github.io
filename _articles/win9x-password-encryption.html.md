---
title: 'Configure password encryption level in Windows 9x'
date: '2003-09-19T21:28:42+02:00'
permalink: /article/win9x-password-encryption.html
author: Snakefoot
excerpt: 'How to configure the password encryption level for better security.'
type: post
id: 210
categories:
    - windows-95_file-sharing
    - windows-98_file-sharing
    - windows-me_file-sharing
tags:
    - encryption
    - password
    - windows-domain
---
A low Password Encryption level is used by default to give a higher level of compatibility, but makes it easy for an intruder to use a network sniffer for discovering other user's username and password.  
  
 Note before Win95/Win98/WinMe can be configured to use a higher level of encryption, then one have to install the Directory Services Client, which is found on the Win2k Install-Cd (X:\\Clients\\Win9x\\Dsclient.exe), and Win95 also requires that Winsock2 update and at least <a href="https://www.bing.com/search?q=KB+285189+Q285189" title="Dial-Up Networking 1.4 Upgrade Is Available [Q285189]" rel="nofollow">DUN 1.3+</a> is installed.  
 If doing domain logon learn <a href="https://www.bing.com/search?q=KB+249841+Q249841" title="INFO: How Windows 95 and Windows 98 Directory Services Client Uses Active Directory Site Information [Q249841]"), and check that the [DNS Server is properly configured](http://support.microsoft.com/kb/237675 "Setting Up the Domain Name System for Active Directory [Q237675]" rel="nofollow">How the DSClient uses DNS lookup</a> or it can cause slow logon, as it has to timeout before it uses Netbios.  
  
 Configure the Lan Manager Compatibility level in Challenge/Response:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\LSA\]  
>  LMCompatibility = 3 (Default 0)  
>   
>  Level 0 = Client uses LM and NTLM  
>  Level 3 = Client only uses NTML2  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+239869+Q239869" rel="nofollow" title="How to enable NTLM 2 authentication [Q239869]">MS KB239869</a>

 Configure the LanManager Security Support Provider (SSP):
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\control \\LSA \\MSV1\_0\]  
 >  NtlmMinClientSec = 0x20080030 (Default 0)  
 >   
 >  0x20080030 = 128 Bit, NTLM2, Message Confidentiality, Message Integrity  
 >   
 >  Note to reach 128 bit encryption one have to install the Internet Explorer with 128 encryption before installing the Directoy Services Client.  
 >   
 >  More Info <a href="https://www.bing.com/search?q=KB+239869+Q239869" rel="nofollow" title="How to enable NTLM 2 authentication [Q239869]">MS KB239869</a>

 The LanManager can be configured not to require Challenge/Response(CHAP), but also allow Password Authentication Protocol(PAP):
 
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\VNETSUP\]  
 >  EnablePlainTextPassword = 1 (Default = 0 and the most secure)  
 >   
 >  More Info <a href="https://www.bing.com/search?q=KB+185612+Q185612" rel="nofollow" title="Invalid Password Error Message After You Upgrade to Windows 98 [Q185612]">MS KB185612</a>  
 >  More Info <a href="https://www.bing.com/search?q=KB+187228+Q187228" rel="nofollow" title="Unable to Connect to a Samba Server with Windows 98 [Q187228]">MS KB187228</a>

 More Info <a href="https://www.bing.com/search?q=KB+249841+Q249841" rel="nofollow" title="INFO: How Windows 95 and Windows 98 Directory Services Client Uses Active Directory Site Information [Q249841]">MS KB249841</a>  
 More Info <a href="https://www.bing.com/search?q=KB+288358+Q288358" rel="nofollow" title="How to install the Active Directory client extension">MS KB288358</a> (Download original DsClient.exe)  
 More Info <a href="https://www.bing.com/search?q=KB+283261+Q283261" rel="nofollow" title="Version Conflicts with the Directory Service Client Version of Windows 95 and Windows 98 System Files [Q283261]">MS KB283261</a> (Flaw in DsClient.exe)  
 More Info <a href="https://www.bing.com/search?q=KB+323455+Q323455" rel="nofollow" title="Availability of the Directory Services Client Update for Windows 98 [Q323455]">MS KB323455</a> (Description of [Hotfix](ftp://ftp.catalyst.com/pub/cstools/support/dsclient.exe "Mirror of 5.0.2920.5") for DsClient.exe) (Replaces MS KB323466)  
 More Info <a href="https://www.bing.com/search?q=KB+555038+Q555038" rel="nofollow" title="How to enable Windows 98/ME/NT clients to logon to Windows 2003 based Domains [Q555038]">MS KB555038</a> (Using DsClient.exe)  
  
 Related [Description of password encryption level over network](/article/windows-password-encryption.html)