---
title: 'System Restore Service'
date: '2003-06-05T19:12:24+02:00'
permalink: /article/winnt-services-srservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the System Restore service.'
type: post
id: 601
categories:
    - windows-xp_services
tags: []
---
##### Description:

 Performs system restore functions that takes images of your registry and files and enables one to return to a previous image. It will automatically create restore points when events like install large software packages or service packs.  
  
 It is recommended only to have System Restore to monitor the file operations on the system partition, and then have a secondary partition with system restore deactivated for 3rd party applications, especially if they are disk intensive like compiling. This will also keep System Restore from stop working in case a non-system partition monitored by System Restore is out of space (Less than 200 MByte free space).  
  
 Note to configure the System Restore go to Control Panel -&gt; System -&gt; System Restore-Tab. If having System Restore enabled and having several partitions, then one can also deactivate System Restore for selected partitions (But not the system partition). To configure how often to make a system restore point change this DWORD registry key:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\SystemRestore\]  
>  RPGlobalInterval = 43200 (Default = 86400 secs, 24 hours)

 Note if disabling system restore then all restore points saved (C:\\System Volume Information\\\_Restore) will be deleted. Though this action can be necessary if a virus has infected the files in a system restore point.  
  
 Note that some AntiVira software uses a large amount of resource on monitoring the ?:\\System Volume Information\\ folder. It can be a good idea to exclude the folders so they are not scanned.  
  
 Note to start the system restore wizard from a command prompt (F.ex. if booting into "Safe Mode with Command Prompt"):
> %windir%\\system32\\restore\\rstrui.exe  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+304449+Q304449" rel="nofollow" title="How to start the System Restore tool at a command prompt in Windows XP [Q304449]">MS KB304449</a>

 Note if restored the system to a restore point before WinXP being activated, then one can try to reactivate without contacting Microsoft:
1. Boot into Safe-mode and go to the folder %systemroot%\\system32
2. Rename wpa.dbl to wpa.noact (To make a backup)
3. Rename wpa.bak to wpa.dbl
4. Reboot into Normal-mode
 
 Note if System Restore fails to create restore points or operate properly, then one can try to reinstall it by running this command:
 > rundll32.exe advpack.dll,LaunchINFSection %Windir%\\Inf\\sr.inf

 More Info <a href="https://www.bing.com/search?q=KB+283073+Q283073" rel="nofollow" title="How to Disable the System Restore Configuration User Interface [Q283073]">MS KB283073</a>  
 More Info <a href="https://www.bing.com/search?q=KB+295299+Q295299" rel="nofollow" title="HOW TO: Use the System Restore Utility with Windows Management Instrumentation in Windows XP [Q295299]">MS KB295299</a>  
 More Info <a href="https://www.bing.com/search?q=KB+299904+Q299904" rel="nofollow" title="The System Restore Utility May Be Suspended on a System Drive Even Though There Is Enough Disk Space [Q299904]">MS KB299904</a>  
 More Info <a href="https://www.bing.com/search?q=KB+301224+Q301224" rel="nofollow" title="System Restore 'Restore Points' Are Missing or Deleted [Q301224]">MS KB301224</a>  
 More Info <a href="https://www.bing.com/search?q=KB+302796+Q302796" rel="nofollow" title="Troubleshooting System Restore in Windows XP [Q302796]">MS KB302796</a>  
 More Info <a href="https://www.bing.com/search?q=KB+306084+Q306084" rel="nofollow" title="HOW TO: Restore the Operating System to a Previous State in Windows XP [Q306084]">MS KB306084</a>  
 More Info <a href="https://www.bing.com/search?q=KB+310405+Q310405" rel="nofollow" title="How to Turn On and Turn Off System Restore in Windows XP [Q310405]">MS KB310405</a>  
 More Info <a href="https://www.bing.com/search?q=KB+814833+Q814833" rel="nofollow" title="PRB: Windows System Restore Does Not Monitor Windows Installer Patch (.msp) Files [Q814833]">MS KB814833</a>  
 More Info [MSDN: FAQ Regarding System Restore in WinXP](http://microsoft.com/technet/itcommunity/Newsgroups/FAQSRWXP.asp "Frequently Asked Questions Regarding System Restore in Windows XP")  
 More Info [Technet: Microsoft Windows XP System Restore](http://msdn.microsoft.com/library/en-us/dnwxp/html/windowsxpsystemrestore.asp)  
  
##### Recommended State:

- Automatic, if you willing to spend some extra resources on having a safety net incase something goes fubar.
- Disabled, if wanting to save resources and ready to a clean/repair install when one day having messed up your computer.

##### Default State:

- Automatic

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Srservice)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)