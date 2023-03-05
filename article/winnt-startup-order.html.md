---
title: 'Program startup order in Windows NT'
date: '2004-02-15T02:04:12+01:00'
status: publish
permalink: /article/winnt-startup-order.html
author: Snakefoot
excerpt: 'Description of where and in what order programs are loaded at startup.'
type: post
id: 184
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - boot-time
    - group-policy
    - scheduled-task
post_format: []
tags:
    - 'boot-time,group-policy,scheduled-task'
---
The order of which applications are loaded and where they are loaded from:

1. [BootExecute](/article/winnt-boot-disk-check.html)  
   \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Session Manager\]  
   BootExecute=
2. [Services](/article/winnt-services-config.html)
  - [Task Scheduler](/article/winnt-services-schedule.html) will look in the Scheduled Tasks folder for jobs to execute.
3. **User enters username and password and performs logon**
4. **UserInit** (Login script is performed - More Info [MS KB198642](http://support.microsoft.com/kb/198642 "Overview of Logon, Logoff, Startup, and Shutdown Scripts in Windows 2000 [Q198642]"))  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
   UserInit=userinit.exe
5. **Shell** (Started by Userinit.exe)  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
   Shell=explorer.exe
6. **All Users-RunOnce**  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\RunOnce\]
7. **All Users-Run**  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Run\]
8. **All Users-RunOnceEx**  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\RunOnceEx\]
9. **All Users-RunEx**  
   \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\RunEx\]
10. **Current User-RunOnce**  
   \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\RunOnce\]
11. **Current User-Run**  
   \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Run\]
12. **Current User-RunOnceEx**  
   \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\RunOnceEx\]
13. **Current User-RunEx**  
   \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\RunEx\]
14. **Common Startup Folder in the Start-Menu for All Users**
15. **Startup Folder in the Start-Menu for Current User**
 
 More Info [MS KB170086](http://support.microsoft.com/kb/170086 "System32 Folder Opens When Logging on to Windows XP, Windows 2000, or Windows NT 4.0 [Q170086]")  
 More Info [MS KB232509](http://support.microsoft.com/kb/232509 "Syntax for the RunOnceEx Registry Key [Q232509]")  
 More Info [MS KB284193](http://support.microsoft.com/kb/284193 "How to run a logon script one time when a new user logs on [Q284193]")  
 More Info [MS KB310593](http://support.microsoft.com/kb/310593 "Description of the RunOnceEx Registry Key [Q310593]")  
 More Info [MS KB314488](http://support.microsoft.com/kb/314488 "How to Modify the List of Programs that Run When You Start Windows XP [Q314488]")  
 More Info [MS KB314866](http://support.microsoft.com/kb/314866 "A Definition of the Run Keys in the Windows XP Registry [Q314866]")  
 More Info [MS KB321707](http://support.microsoft.com/kb/321707 "HOW TO: Automatically Run Programs When Users Log On to Windows 2000 Terminal Services [Q321707]")  
  
 Note if one of the Run-sections includes an invalid entry (Uses a path that doesn't exist), then Windows might open at folder at startup. Use [Msconfig](/article/win2k-msconfig.html) or [Startup.CPL](/article/windows-startup-order.html#STARTUP_CPL) to check the entries.  
  
 Note the group policies are by default applied to machine before the user is allowed to perform login. Though it can introduce a delay before the logon window is shown, as it first has to wait for the network to initialize and then contact the domain controller. It possible to configure whether it should wait for the domain controller:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Policies \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  SyncForegroundPolicy = 1 (0 = Do not wait for network to be initialized; WinXP+)  
>   
>  \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\System\]  
>  SynchronousMachineGroupPolicy = 1 (0 = Do not wait for domain controller to apply machine policies)  
>   
>  More Info [MS KB304970](http://support.microsoft.com/kb/304970 "Scripts May Not Run Before Windows Explorer Starts Even Though the "Run Logon Scripts Synchronously" Setting is Enabled [Q304970]")  
>  More Info [MS KB305293](http://support.microsoft.com/kb/305293 "Description of the Windows XP Professional Fast Logon Optimization Feature [Q305293]")

 Note Winlogon.exe controls the login process, by loading user registry, applying user group policies, and the launch of UserInit.exe. The UserInit.exe performs login scripts and executes program specified in Shell=. One can configure the behavior of Winlogon.exe:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\System\]  
>  SynchronousUserGroupPolicy = 1 (0 = Do not wait for domain controller to apply user policies)  
>   
>  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\System\]  
>  RunLogonScriptSync = 1 (0 = Do not wait for script to finish before starting shell)  
>   
>  More Info [MS KB265016](http://support.microsoft.com/kb/265016 "How to Run a Domain Logon Script in the Foreground with the Start.exe Command-Line Tool [Q265016]")  
>  More Info [MS KB258286](http://support.microsoft.com/kb/258286 "HOW TO: Assign a Logon Script to a Profile for a Local User in Windows 2000 [Q258286]")  
>  More Info [MS KB315245](http://support.microsoft.com/kb/315245 "How to Assign a Logon Script to a Profile for a Local User [Q315245]")

 Note during boot Windows might display one or more popup messsages, if using the [EventLog](/article/winnt-services-eventlog.html) to monitor these popup messages and the popup messages are unwanted, then they can be disabled:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control\\ Windows\]  
>  NoPopUpsOnBoot = 1 (0 = Show popup messages during bootup)  
>   
>  More Info [MS KB924690](http://support.microsoft.com/kb/924690 "Error message when you start Windows Server 2003 SP1 for the first time: "Windows could not be started as configured" [Q924690]")

 Related [Use SHIFT-key to prevent launch of 6-15](/article/windows-startup-order.html)  
  
 Credits [Greatis.com](http://greatis.com/)