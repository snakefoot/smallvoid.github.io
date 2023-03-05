---
title: 'Windows Update / Automatic Updates'
date: '2002-08-06T23:28:49+02:00'
status: publish
permalink: /article/winnt-services-wuauserv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Automatic Updates service.'
type: post
id: 523
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - automatic-updates
    - 'Windows Update'
post_format: []
tags:
    - 'windows-update,automatic-updates'
---
##### Description:

 Enables automatic monitoring, download and installation of critical Windows updates. If the service is disabled the operating system can still be updated manually.  
  
 Note if wanting to disable this service one should first turn off the Automatic Updating feature:  
- Win2k SP3+: **Control Panel** -&gt; **Automatic Updates**-applet.
- WinXP/Win2k3: Right click **My Computer**, select **Properties** and go to **Automatic Updates**-tab.
 
 Note after WinXP SP2 one cannot use the Start-Menu shortcut (WUpdMgr.exe) without having this service running, but the direct URL [windowsupdate.microsoft.com](http://windowsupdate.microsoft.com/) still works.  
  
 Related [How to configure the behavior of Automatic Updates](/article/winnt-automatic-updates-config.html)  
 Related [Configure and troubleshoot Automatic Updates](/article/winnt-automatic-updates-repair.html)  
 Related [Fix a non-working Windows Update](/article/repair-windows-update.html)  
  
 More Info [MS KB283629](http://support.microsoft.com/kb/283629 "HOW TO: Configure Automatic Updates to Prompt You Before You Download Updates in Windows XP [Q283629]")  
 More Info [MS KB294871](http://support.microsoft.com/kb/294871 "Description of the Automatic Update Feature in Windows XP [Q294871]")  
 More Info [MS KB306525](http://support.microsoft.com/kb/306525 "HOW TO: Configure and Use Automatic Updates in Windows XP [Q306525]")  
 More Info [MS KB327838](http://support.microsoft.com/kb/327838 "HOW TO: Schedule Automatic Updates in Windows XP and Windows 2000 [Q327838]")  
 More Info [MS KB327850](http://support.microsoft.com/kb/327850 "HOW TO: Configure and Use Automatic Updates in Windows 2000 [Q327850]")  
  
##### Recommended state:

- Automatic, if you don't want the hassle of keeping an eye on Windows.
- Disabled, if you are manually monitoring when Microsoft issues updates for your Windows version.

##### Default State:

- Automatic
- Vista/Win7: Automatic (Delayed Start)

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (wuauserv)

##### Supports:

- none

##### Depends:

- [Cryptographic Services](/article/winnt-services-cryptsvc.html) (WinXP only, Unofficial)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) (Vista+)