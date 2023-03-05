---
title: 'Configure and troubleshoot Secondary Logon service'
date: '2000-07-23T16:07:25+02:00'
status: publish
permalink: /article/winnt-secondary-logon-config.html
author: Snakefoot
excerpt: 'How to use the Secondary Logon service to start an application with different user credentials.'
type: post
id: 589
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - runas
    - scheduled-task
post_format: []
tags:
    - 'runas,scheduled-task'
---
[Secondary Logon](/article/winnt-services-seclogon.html) can be hidden from the GUI, so one doesn't see the option "Run as different user" when starting a program with this DWORD value:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  HideRunAsVerb = 1  
>   
>  More Info [MS KB830568](http://support.microsoft.com/kb/830568 "How to disable the Run As feature on a Windows Server 2003-based or on a Windows XP-based computer [Q830568]")

 Note with Win2k SP4 a new policy was created making it possible to configure what accounts(Default:Administrators and SYSTEM), which are allowed to impersonate other accounts:
1. Open **Control Panel** and open **Administrative Tools** and double click **Local Security Policy**
2. Expand **Local Policies** and click **User Rights Assignment**
3. In the right pane double click **Impersonate a client after authentication**
4. Press **Add...** to enable other users to impersonate other accounts
 
 More Info [MS KB821546](http://support.microsoft.com/kb/821546 "Overview of the "Impersonate a Client After Authentication" and the "Create Global Objects" Security Settings [Q821546]")  
  
 Note one can also run applications as another user from the command line using "RUNAS", though in Win2k it will prompt for password unless using [Sanur](http://www.commandline.co.uk/sanur/ "Runas Automation Utility"), [CPUA](http://www.joeware.net/ "Create Process As User - Joe Richards"), [LSrunas](http://www.lansweeper.com/ls/lsrunas.aspx "LanSweeper RunAs") or [Steel Run-As](http://www.steelsonic.com/). WinXP Professional (Not Home) extends "RUNAS" with the /savecred option where one is only prompted for the password once. To see all options available:
> runas /?  
>   
>  More Info [MS KB294676](http://support.microsoft.com/kb/294676 "HOW TO: Enable and Use the "Run As" Command When Running Programs [Q294676]")  
>  More Info [MS KB893677](http://support.microsoft.com/kb/893677 "You receive the "Game requires Administrative rights to play" error message when you try to play a game in Windows XP Professional [Q893677]")

 Note in WinNT4 one can use the Super User Service Starter SUSS.EXE and the tool SU.EXE (Found in the NT reskit):
> SUSS.EXE -install  
>   
>  ECHO Password | SU.EXE Username UserMgr.exe  
>   
>  SU\_USERNAME - Environment variable for default user name to SU.  
>  SU\_PASSWORD - Environment variable for password to SU. Avoids password prompting.  
>  SU\_DOMAIN - Environment variable for domain name referenced by SU.  
>  SU\_COMMANDLINE - Environment variable for command line run by SU.  
>  SU\_DESKTOP - Environment variable for windowstation and desktop targeted by SU.  
>   
>  More Info [MS KB829640](http://support.microsoft.com/kb/829640 "Windows logon dialog box is not available when you run the Super User utility [Q829640]")

 Note another way of running an application as another user is to create a [scheduled task](/article/winnt-services-schedule.html) where it is possible to specify username and password.