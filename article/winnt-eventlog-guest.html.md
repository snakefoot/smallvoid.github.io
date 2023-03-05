---
title: 'Restrict guest access to event logs'
date: '2002-10-12T20:36:18+02:00'
status: publish
permalink: /article/winnt-eventlog-guest.html
author: Snakefoot
excerpt: 'The system event log can contain information, which can be used compromise the security.'
type: post
id: 452
category:
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - event-log
    - guest-account
    - user-account
post_format: []
tags:
    - 'event-log,guest-account,user-account'
---
Guests are by default allowed to access the Event Logs of a machine(Even over the network). The are 3 event logs on a machine Application-, Security- and System-EventLog.  
  
 To block guest access to the EventLogs set the following DWORD keys (Blocked by default on Windows XP/2003):

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\EventLog \\Application\]  
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\EventLog \\System\]  
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\EventLog \\Security\]  
> RestrictGuestAccess = 1 (0 = Enable Guest Access, 1 = Disable Guest Access)  
>   
>  More info [MS KB174074](http://support.microsoft.com/kb/174074 "Security Event Descriptions [Q174074]")  
>  More info [MS KB842209](http://support.microsoft.com/kb/842209 "You receive an "Access is denied" error message when you try to access an event log on a Windows Server 2003-based computer or on a Windows 2000-based computer [Q842209]")  
>  More info [MS KB888189](http://support.microsoft.com/kb/888189 ""Unable to complete the operation on <event log>. Access is denied." error message when you try to access a log on a Windows Server 2003-based computer [Q888189]")

 If in a domain then the access to the eventlogs can be configured through the group policy editor. The policies can be found at Computer Configuration -&gt; Windows Settings &gt; Security Settings -&gt; Event Log:
- "Prevent local guests group from accessing system log" (WinXP/Win2k3) / "Restrict guest access to system log" (Win2k)
- "Prevent local guests group from accessing application log" (WinXP/Win2k3) / "Restrict guest access to application log" (Win2k)
 
 It is also possible to control the access to the event logs by using [NTFS permissions](/article/ntfs-access-control.html) and control who have access to the folder or the event log files:
 > %systemroot%\\system32\\config

 Windows 2003 introduces a new way of controlling the access to the event logs, by using Security Descriptor Definition Language ([SDDL](http://msdn.microsoft.com/library/en-us/secauthz/security/security_descriptor_definition_language.asp)) syntax. Where one can specify a SID along with the allowed access. More info [MS KB323076](http://support.microsoft.com/kb/323076 "HOW TO: Set Event Log Security Locally or by Using Group Policy in Windows Server 2003 [Q323076]")  
  
 Note that if a service is configured to run with guest credentials, then it will not be allowed to access the EventLogs.  
  
 Note it might be possible for other accounts than the guest account to access the Event Logs if the following Multi-String (Regedt32) exists:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\SecurePipeServers \\Winreg \\Allowed Paths\]  
> Machine = "System\\CurrentControlSet\\Services\\Eventlog"  
>   
>  More info [MS KB245128](http://support.microsoft.com/kb/245128 "HOW TO: Restrict Remote Access to Event Viewer on Windows NT Server 4.0 [Q245128]")  
>  More info [MS KB268559](http://support.microsoft.com/kb/268559 "Domain Users Can Remotely Access Event Logs [Q268559]")