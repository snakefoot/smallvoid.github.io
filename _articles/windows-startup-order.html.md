---
title: 'Bypass the loading of programs at Windows startup'
date: '2001-01-01T01:51:22+01:00'
permalink: /article/windows-startup-order.html
author: Snakefoot
excerpt: 'Holding down the SHIFT key during Windows startup will stop applications from loading.'
type: post
id: 183
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-95_troubleshoot
    - windows-98_troubleshoot
    - windows-me_troubleshoot
    - windows-nt4_troubleshoot
    - windows-xp_troubleshoot
tags:
    - boot-time
    - msconfig
    - system-recovery
---
During startup Microsoft Windows checks several "hidden" places for whether it should launch any 3rd party applications. Certain applications have a tendency to place themselves in one of these places, so they are automatically started when Windows is started.  
  
 If holding down the SHIFT-key while Windows starts, then it will tell Windows not to check the different places for applications to start. This can be useful in case an application is preventing the machine from starting properly, making it possible to uninstall the application or configure it not to start.  
 The SHIFT-key will also in WinNT+ disable the [automatic login](/article/winnt-automatic-logon.html), which can be useful in case the default user profile has become corrupted.  
  
<a name="STARTUP_CPL"></a> To see the applications currently set to launch themselves, then one should use these utilities:

- [Startup.CPL](http://www.mlin.net/) (Recommended)
- [Autoruns](http://www.sysinternals.com/Utilities/Autoruns.html)
- Msconfig [Win9x](/article/win95-msconfig.html) [WinNT](/article/win2k-msconfig.html)
 
 Note it is possible to control the order in which the items in the StartUp-folder is started. One should just prefix the shortcuts in the Startup-folder with with 1\_&lt;filename&gt;.lnk  
 Though if the applications shouldn't launch simultaneously then a batch file should be used, using the start /wait option.  
  
 Related [Find programs which starts automatically in Win9x/Me](/article/win9x-startup-order.html)  
 Related [Find programs which starts automatically in WinNT+](/article/winnt-startup-order.html)  
  
 More Info <a href="https://www.bing.com/search?q=KB+81606+Q81606" rel="nofollow" title="Disabling the Startup Group in Windows [Q81606]">MS KB81606</a>