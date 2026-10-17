---
title: 'Configure and troubleshoot Windows Management Instrumentation'
date: '2000-07-23T22:23:09+02:00'
permalink: /article/winnt-wmi-config.html
author: Snakefoot
excerpt: 'Description of how to repair the Windows Management Instrumentation (WMI) repository.'
type: post
id: 620
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-xp_troubleshoot
    - windows-vista_troubleshoot
tags:
    - wmi
---
[Windows Management Instrumentation (WMI)](/article/winnt-services-winmgmt.html) will fail to start or operate properly if the WMI repository is corrupt. Depending on what version of Windows, there are different ways to repair/rebuild/reset the WMI repository:
- Windows Vista/2008:
  > winmgmt /verifyrepository  
  >  winmgmt /salvagerepository
- Windows XP (Requires atleast SP2):
  > rundll32 wbemupgd, UpgradeRepository
- Windows 2003 (Requires atleast SP1):
  > rundll32 wbemupgd, RepairWMISetup
- Other versions (Note it will reset the [ICS and ICF](/article/winnt-services-sharedaccess.html) configuration): 
  1. winmgmt /clearadap
  2. winmgmt /kill
  3. winmgmt /unregserver
  4. winmgmt /regserver
  5. winmgmt /resyncperf
  6. net stop winmgmt
  7. del %windir%\\system32\\Wbem\\Repository\\\*.\* /s
  8. net start winmgmt
  9. %windir%\\system32\\wbem\\wbemtest.exe

 More Info [MS Technet - WMI Isn't Working!](http://www.microsoft.com/technet/scriptcenter/topics/help/wmi.mspx "Troubleshooting Problems with WMI Scripts and the WMI Service")  
 More Info <a href="https://www.bing.com/search?q=KB+216738+Q216738" rel="nofollow" title="SMS: WMI Terms and Concepts [Q216738]">MS KB216738</a>  
 More Info <a href="https://www.bing.com/search?q=KB+266416+Q266416" rel="nofollow" title="How to Troubleshoot WinMgmt-Based Performance Counter Errors [Q266416]">MS KB266416</a>  
 More Info <a href="https://www.bing.com/search?q=KB+305992+Q305992" rel="nofollow" title="Restore Point Creation Takes Up to 10 Minutes if the WMI Service Is Not Running [Q305992]">MS KB305992</a>  
 More Info <a href="https://www.bing.com/search?q=KB+823775+Q823775" rel="nofollow" title="Error Message: The Windows Management Instrumentation (WMI) Might Be Corrupted [Q823775]">MS KB823775</a> (Replaces MS KB319101)  
 More Info <a href="https://www.bing.com/search?q=KB+875605+Q875605" rel="nofollow" title="How to troubleshoot WMI-related issues in Windows XP SP2 [Q875605]">MS KB875605</a>  
  
 Note if for some obscure reason wanting to disable the [WMI service](/article/winnt-services-winmgmt.html), then WinMgmt.exe will complain, this can be solved by running these commands before disabling:
> winmgmt /clearadap  
>  winmgmt /kill  
>  winmgmt /unregserver

 To see all parameters for WinMgmt.exe:
 > winmgmt /?