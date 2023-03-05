---
title: 'Configure and troubleshoot Print Spooler service'
date: '2000-06-06T16:21:24+02:00'
status: publish
permalink: /article/winnt-printer-spooler-config.html
author: Snakefoot
excerpt: 'How to configure the priority and logging level of the Printer Spooler service.'
type: post
id: 574
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - print-spooler
    - printer
post_format: []
tags:
    - 'printer,print-spooler'
---
[Print Spooler](/article/winnt-services-spooler.html) service is required to print documents or to install printers. If the service is not started, then it will instead give an error message (The usual solution is to start the service or clear the [spool directory](/article/winnt-print-spool-folder.html) or [reinstall printer drivers](/article/winnt-reinstall-printer-driver.html)):
> *Printer operation cannot continue due to lack of resources. The print subsystem is unavailable  
>   
>  The RPC Server Is Unavailable  
>   
>  Operation cannot be completed.*  
>   
>  More Info [MS KB158042](http://support.microsoft.com/kb/158042 ""Operation Could Not Be Completed" When Using Add Printer Wizard [Q158042]")  
>  More Info [MS KB221092](http://support.microsoft.com/kb/221092 "Applications Hang When Printing to a Printer Set to "Use Printer Offline" [Q221092]")  
>  More Info [MS KB244921](http://support.microsoft.com/kb/244921 ""The Print Subsystem Is Unavailable" Error Message After Installing Office 2000 [Q244921]")  
>  More Info [MS KB255197](http://support.microsoft.com/kb/255197 "Cannot Add a Printer Port, Access Violation in Spools.exe Occurs in Windows NT Server 4.0 [Q255197]")  
>  More Info [MS KB308028](http://support.microsoft.com/kb/308028 "Resources for Troubleshooting Printing Problems in Windows XP [Q308028]")  
>  More Info [MS KB314085](http://support.microsoft.com/kb/314085 "Troubleshooting General Printing Problems in Windows XP [Q314085]")  
>  More Info [MS KB811348](http://support.microsoft.com/kb/811348 "Error message when you try to add a new printer [Q811348]")  
>  More Info [MS KB832219](http://support.microsoft.com/kb/832219 "Users Cannot Print After You Install a Service Pack or Printer Hotfix on a Server [Q832219]")

 To configure the priority of the print spooler threads use these DWORD registry values:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print\]  
>  SpoolerPriority = 1 (0 = Normal, 1 = Higher, 0xFFFFFFFF = Lower)  
>  SchedulerThreadPriority = 1 (0 = Normal, 1 = Higher, 0xFFFFFFFF = Lower)  
>  PortThreadPriority = 1 (0 = Normal, 1 = Higher, 0xFFFFFFFF = Lower)  
>   
>  More Info [MS KB103411](http://support.microsoft.com/kb/103411 "Windows NT Parallel Ports Do Not Use Interrupts [Q103411]")  
>  More Info [MS KB156689](http://support.microsoft.com/kb/156689 "How to Change Print Job Priority in Windows NT Server 4.0 [Q156689]")

 To configure the output to the EventLog:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print \\Providers\]  
>  EventLog = 0 (0 = Disabled, 1 = Errors, 2 = Warnings, 4 = Informative, 7 = All)  
>   
>  More Info [MS KB115841](http://support.microsoft.com/kb/115841 "Turning Off Print Job Logging in the System Log [Q115841]")

 To configure whether to make a notify popup when print job finished. Open Control Panel -&gt; Printers -&gt; File-menu -&gt; Server-Properties -&gt; Advanced-Tab -&gt; Untick "Notify when remote documents are printed". (This should be reflected with this registry key)
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print \\Providers\]  
>  NetPopup = 0 (0 = Disabled, 1 = Enabled)  
>   
>  More Info [MS KB283102](http://support.microsoft.com/kb/283102 "Windows NT4.0 Print Servers May Experience Paged Pool Leak on FsRt Pooltag [Q283102]")  
>  More Info [MS KB122160](http://support.microsoft.com/kb/122160 "Disabling Printing Notification Dialog Boxes in Windows [Q122160]")  
>   
>  Related [Disable Printer Balloon Tips in WinXP](/article/winnt-balloon-tip.html)

 To configure whether shared printers should use bandwidth to announce themselves to the entire network (Internet included):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print\]  
>  DisableServerThread = 1 (1 = Hidden, 0 = Visible in Network Neighborhood)  
>   
>  More Info [MS KB227908](http://support.microsoft.com/kb/227908 "Domain-Level Printer List Is Not Refreshed [Q227908]")  
>  More Info [MS KB131902](http://support.microsoft.com/kb/131902 "Printer Browse Thread May Cause Extensive Network Traffic [Q131902]")