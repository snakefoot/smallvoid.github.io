---
title: 'System Restore Service'
date: '2003-06-05T19:12:24+02:00'
status: publish
permalink: /article/winnt-services-srservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the System Restore service.'
type: post
id: 601
category:
    - 'Services Guide'
tag: []
post_format: []
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
>  More Info [MS KB304449](http://support.microsoft.com/kb/304449 "How to start the System Restore tool at a command prompt in Windows XP [Q304449]")

 Note if restored the system to a restore point before WinXP being activated, then one can try to reactivate without contacting Microsoft:
1. Boot into Safe-mode and go to the folder %systemroot%\\system32
2. Rename wpa.dbl to wpa.noact (To make a backup)
3. Rename wpa.bak to wpa.dbl
4. Reboot into Normal-mode
 
 Note if System Restore fails to create restore points or operate properly, then one can try to reinstall it by running this command:
 > rundll32.exe advpack.dll,LaunchINFSection %Windir%\\Inf\\sr.inf

 More Info [MS KB283073](http://support.microsoft.com/kb/283073 "How to Disable the System Restore Configuration User Interface [Q283073]")  
 More Info [MS KB295299](http://support.microsoft.com/kb/295299 "HOW TO: Use the System Restore Utility with Windows Management Instrumentation in Windows XP [Q295299]")  
 More Info [MS KB299904](http://support.microsoft.com/kb/299904 "The System Restore Utility May Be Suspended on a System Drive Even Though There Is Enough Disk Space [Q299904]")  
 More Info [MS KB301224](http://support.microsoft.com/kb/301224 "System Restore "Restore Points" Are Missing or Deleted [Q301224]")  
 More Info [MS KB302796](http://support.microsoft.com/kb/302796 "Troubleshooting System Restore in Windows XP [Q302796]")  
 More Info [MS KB306084](http://support.microsoft.com/kb/306084 "HOW TO: Restore the Operating System to a Previous State in Windows XP [Q306084]")  
 More Info [MS KB310405](http://support.microsoft.com/kb/310405 "How to Turn On and Turn Off System Restore in Windows XP [Q310405]")  
 More Info [MS KB814833](http://support.microsoft.com/kb/814833 "PRB: Windows System Restore Does Not Monitor Windows Installer Patch (.msp) Files [Q814833]")  
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