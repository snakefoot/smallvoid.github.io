---
title: 'Configure password encryption level in Windows NT'
date: '2003-09-19T21:41:11+02:00'
status: publish
permalink: /article/winnt-password-encryption.html
author: Snakefoot
excerpt: 'How to configure the password encryption level for better security.'
type: post
id: 211
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - encryption
    - ntlm
    - ntlm2
    - password
    - windows-domain
post_format: []
tags:
    - 'password,encryption,ntlm2,ntlm,windows-domain'
---
A low Password Encryption level is used by default to give a higher level of compatibility, but makes it easy for an intruder to use a network sniffer for discovering other user's username and password.  
  
 Configure the Lan Manager Compatibility level (WinNT4 SP6+):

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\control \\LSA\]  
>  LMCompatibilityLevel = 3 (Default 0)  
>   
> [List of possible Lan Manager Compatibility levels](/article/windows-password-encryption.html#LMCompatibilityLevel)

 Configure the NT LanManager (NTLM) Security Support Provider (SSP) (WinNT4 SP4+):
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\control \\LSA \\MSV1\_0\]  
>  NtlmMinClientSec = 0x20080030 (Default 0)  
>  NtlmMinServerSec = 0x20080030 (Default 0)  
>   
> [List of possible Security Support Provider levels](/article/windows-password-encryption.html#NtlmMinSec)

 The LanManager can be configured not to require Challenge/Response(CHAP), but also allow Password Authentication Protocol(PAP) (WinNT4 SP3+):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Rdr \\Parameters\]  
>  EnablePlainTextPassword = 1 (Default = 0 and the most secure)  
>   
>  More Info [MS KB166730](http://support.microsoft.com/kb/166730 "Unencrypted Passwords May Cause SP3 to Fail to Connect to SMB Servers [Q166730]")  
>  More Info [MS KB256322](http://support.microsoft.com/kb/256322 "Error Occurs When You Configure IIS to Use a Samba Network Share As Its Root [Q256322]")

 The LanManager can be configured not to require Challenge/Response(CHAP), but also allow Password Authentication Protocol(PAP) (Win2k+):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanWorkStation \\Parameters\]  
>  EnablePlainTextPassword = 1 (Default = 0 and the most secure)  
>   
>  More Info [MS KB224287](http://support.microsoft.com/kb/224287 "Err Msg: System Error 1240 Has Occurred. The Account Is Not Authorized to Login from This Station [Q224287]")

 Related [Description of password encryption level over network](/article/windows-password-encryption.html)  
  
 More Info [MS KB236414](http://support.microsoft.com/kb/236414 "Cannot Use Shares with LMCompatibilityLevel set to Only NTLM 2 Authentication [Q236414]")  
 More Info [MS KB318266](http://support.microsoft.com/kb/318266 "A Windows XP Client Cannot Log On to a Windows NT 4.0 Domain [Q318266]")  