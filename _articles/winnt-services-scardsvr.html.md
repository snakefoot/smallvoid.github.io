---
title: 'Smart Card'
date: '2000-07-23T18:49:28+02:00'
permalink: /article/winnt-services-scardsvr.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Smart Card service.'
type: post
id: 596
categories:
    - windows-2000_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
tags:
    - smart-card
---
##### Description:

 It is possible to use a plastic card (smart card) to login instead of using a keyboard to type username if having a smart card reader.  
 This service manages and controls access to a smart card inserted into a smart card reader attached to the computer.  
  
 There is registry entry that can enable additional protection from PKINIT-related vulnerabilities:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Lsa \\Kerberos\]  
>  RequireAsChecksum = 1 (Default WinXP = 0)  
>   
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Lsa \\Kerberos \\Parameters\]  
>  RequireAsChecksum = 1 (Default Win2k/Win2k3 = 0)  
>   
>  Note before enabling this setting on the client-machines, one should make sure that <a href="https://www.bing.com/search?q=KB%20899587%20Q899587" rel="nofollow" title="MS05-042: Vulnerabilities in Kerberos could allow denial of service, information disclosure, and spoofing [Q899587]">MS KB899587</a> is installed on the domain controller or else the smart card login will fail. More info <a href="https://www.bing.com/search?q=KB%20904766%20Q904766" rel="nofollow" title="How to modify the RequireAsChecksum registry entry after you install security update 899587 [Q904766]">MS KB904766</a>

##### Recommended State:

- Manual.

##### Default State:

- Manual

##### Process Name:

- Win7 - [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (SCardSvr)
- Vista - [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (SCardSvr)
- Win2k/WinXP/Win2k3 - SCardSvr.exe (SCardSvr)

##### Supports:

- None

##### Depends:

- [Plug and Play](/article/winnt-services-plugplay.html)