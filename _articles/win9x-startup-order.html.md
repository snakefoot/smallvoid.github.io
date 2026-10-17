---
title: 'Program startup order in Windows 9x'
date: '2004-02-15T01:39:19+01:00'
permalink: /article/win9x-startup-order.html
author: Snakefoot
excerpt: 'Description of where and in what order programs are loaded at startup.'
type: post
id: 181
categories:
    - windows-95_troubleshoot
    - windows-98_troubleshoot
    - windows-me_troubleshoot
tags:
    - boot-time
    - msconfig
---
The order of which applications are loaded and where they are loaded from:

1. **config.sys**
2. **autoexec.bat**
3. **wininit.ini**
4. **winstart.bat**
5. **system.ini**
6. **win.ini**  
   \[Windows\]  
   Load=  
   Run=
7. **All Users-RunServicesOnce**  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\RunServicesOnce\]
8. **All Users-RunServices**  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\RunServices\]
9. **All Users-RunOnce**  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\RunOnce\]
10. **All Users-Run**  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Run\]
11. **All Users-RunOnceEx**  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\RunOnceEx\]
12. **All Users-RunEx**  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\RunEx\]
13. **Current User-RunOnce**  
   \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\RunOnce\]
14. **Current User-Run**  
   \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Run\]
15. **Current User-RunOnceEx**  
   \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\RunOnceEx\]
16. **Current User-RunEx**  
   \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\RunEx\]
17. **Common Startup Folder in the Start-Menu for All Users**
18. **Startup Folder in the Start-Menu for Current User**
 
 More Info <a href="https://www.bing.com/search?q=KB%20137367%20Q137367" rel="nofollow" title="Definition of the RunOnce Keys in the Registry [Q137367]">MS KB137367</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20174018%20Q174018" rel="nofollow" title="Description of the Windows 95 Startup Process [Q174018]">MS KB174018</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20179365%20Q179365" rel="nofollow" title="INFO: Run, RunOnce, RunServices, RunServicesOnce and Startup [Q179365]">MS KB179365</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20232487%20Q232487" rel="nofollow" title="Description of the RunOnceEx Registry Key [Q232487]">MS KB232487</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20243039%20Q243039" rel="nofollow" title="How to Perform a Clean Boot in Windows 95 [Q243039]">MS KB243039</a>  
  
 Note if one of the Run-sections includes an invalid entry (Uses a path that doesn't exist), then Windows might open at folder at startup. Use [Startup.CPL](/article/windows-startup-order.html#STARTUP_CPL) or [Msconfig](/article/win95-msconfig.html) to check the entries.  
  
 Related [Use SHIFT-key to prevent launch of 6-18](/article/windows-startup-order.html)  
  
 Credits [Greatis.com](http://greatis.com/)