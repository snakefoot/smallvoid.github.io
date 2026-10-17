---
title: 'Windows Update / Automatic Updates'
date: '2002-08-06T23:28:49+02:00'
permalink: /article/winnt-services-wuauserv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Automatic Updates service.'
type: post
id: 523
categories:
    - windows-2000_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
tags:
    - automatic-updates
    - windows-update
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
  
 More Info <a href="https://www.bing.com/search?q=KB%20283629%20Q283629" rel="nofollow" title="HOW TO: Configure Automatic Updates to Prompt You Before You Download Updates in Windows XP [Q283629]">MS KB283629</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20294871%20Q294871" rel="nofollow" title="Description of the Automatic Update Feature in Windows XP [Q294871]">MS KB294871</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20306525%20Q306525" rel="nofollow" title="HOW TO: Configure and Use Automatic Updates in Windows XP [Q306525]">MS KB306525</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20327838%20Q327838" rel="nofollow" title="HOW TO: Schedule Automatic Updates in Windows XP and Windows 2000 [Q327838]">MS KB327838</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20327850%20Q327850" rel="nofollow" title="HOW TO: Configure and Use Automatic Updates in Windows 2000 [Q327850]">MS KB327850</a>  
  
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