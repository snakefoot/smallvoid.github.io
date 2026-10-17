---
title: 'Configure and troubleshoot Print Spooler service'
date: '2000-06-06T16:21:24+02:00'
permalink: /article/winnt-printer-spooler-config.html
author: Snakefoot
excerpt: 'How to configure the priority and logging level of the Printer Spooler service.'
type: post
id: 574
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-nt4_troubleshoot
    - windows-xp_troubleshoot
tags:
    - print-spooler
    - printer
---
[Print Spooler](/article/winnt-services-spooler.html) service is required to print documents or to install printers. If the service is not started, then it will instead give an error message (The usual solution is to start the service or clear the [spool directory](/article/winnt-print-spool-folder.html) or [reinstall printer drivers](/article/winnt-reinstall-printer-driver.html)):
> *Printer operation cannot continue due to lack of resources. The print subsystem is unavailable  
>   
>  The RPC Server Is Unavailable  
>   
>  Operation cannot be completed.*  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+158042+Q158042" rel="nofollow" title="'Operation Could Not Be Completed' When Using Add Printer Wizard [Q158042]">MS KB158042</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+221092+Q221092" rel="nofollow" title="Applications Hang When Printing to a Printer Set to 'Use Printer Offline' [Q221092]">MS KB221092</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+244921+Q244921" rel="nofollow" title="'The Print Subsystem Is Unavailable' Error Message After Installing Office 2000 [Q244921]">MS KB244921</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+255197+Q255197" rel="nofollow" title="Cannot Add a Printer Port, Access Violation in Spools.exe Occurs in Windows NT Server 4.0 [Q255197]">MS KB255197</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+308028+Q308028" rel="nofollow" title="Resources for Troubleshooting Printing Problems in Windows XP [Q308028]">MS KB308028</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+314085+Q314085" rel="nofollow" title="Troubleshooting General Printing Problems in Windows XP [Q314085]">MS KB314085</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+811348+Q811348" rel="nofollow" title="Error message when you try to add a new printer [Q811348]">MS KB811348</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+832219+Q832219" rel="nofollow" title="Users Cannot Print After You Install a Service Pack or Printer Hotfix on a Server [Q832219]">MS KB832219</a>

 To configure the priority of the print spooler threads use these DWORD registry values:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print\]  
>  SpoolerPriority = 1 (0 = Normal, 1 = Higher, 0xFFFFFFFF = Lower)  
>  SchedulerThreadPriority = 1 (0 = Normal, 1 = Higher, 0xFFFFFFFF = Lower)  
>  PortThreadPriority = 1 (0 = Normal, 1 = Higher, 0xFFFFFFFF = Lower)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+103411+Q103411" rel="nofollow" title="Windows NT Parallel Ports Do Not Use Interrupts [Q103411]">MS KB103411</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+156689+Q156689" rel="nofollow" title="How to Change Print Job Priority in Windows NT Server 4.0 [Q156689]">MS KB156689</a>

 To configure the output to the EventLog:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print \\Providers\]  
>  EventLog = 0 (0 = Disabled, 1 = Errors, 2 = Warnings, 4 = Informative, 7 = All)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+115841+Q115841" rel="nofollow" title="Turning Off Print Job Logging in the System Log [Q115841]">MS KB115841</a>

 To configure whether to make a notify popup when print job finished. Open Control Panel -&gt; Printers -&gt; File-menu -&gt; Server-Properties -&gt; Advanced-Tab -&gt; Untick "Notify when remote documents are printed". (This should be reflected with this registry key)
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print \\Providers\]  
>  NetPopup = 0 (0 = Disabled, 1 = Enabled)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+283102+Q283102" rel="nofollow" title="Windows NT4.0 Print Servers May Experience Paged Pool Leak on FsRt Pooltag [Q283102]">MS KB283102</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+122160+Q122160" rel="nofollow" title="Disabling Printing Notification Dialog Boxes in Windows [Q122160]">MS KB122160</a>  
>   
>  Related [Disable Printer Balloon Tips in WinXP](/article/winnt-balloon-tip.html)

 To configure whether shared printers should use bandwidth to announce themselves to the entire network (Internet included):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print\]  
>  DisableServerThread = 1 (1 = Hidden, 0 = Visible in Network Neighborhood)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+227908+Q227908" rel="nofollow" title="Domain-Level Printer List Is Not Refreshed [Q227908]">MS KB227908</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+131902+Q131902" rel="nofollow" title="Printer Browse Thread May Cause Extensive Network Traffic [Q131902]">MS KB131902</a>