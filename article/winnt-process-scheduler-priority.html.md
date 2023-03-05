---
title: 'Change processor quantums to tweak application priority'
date: '2001-02-02T14:23:03+01:00'
status: publish
permalink: /article/winnt-process-scheduler-priority.html
author: Snakefoot
excerpt: 'Configure how the process scheduler should split up the processor slots.'
type: post
id: 29
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - cpu
    - process-priority
    - process-scheduler
post_format: []
tags:
    - 'cpu,process-priority,process-scheduler'
---
When running several applications/processes simultaneously then a coordinator/scheduler is needed to make sure that all applications get a fair quantum/slice of the CPU time. The coordinator can be configured in how it gives CPU quantums to the different applications running.

- **Foreground vs. Background**: Foreground boost means that the application currently having focus will get more quantums than other applications, thus it will not be disturbed that much by background processes. Background means that all applications gets equal amount of CPU quantums.
- **Short vs. Long** (Win2k+): Short quantums means that applications can hold the CPU for a short time, thus giving smooth multitasking. Long quantums means that applications can hold the CPU for longer time, thus spending less time on process switching.
- **Variable vs. Fixed** (Win2k+): Variable quantums means that the foreground application can hold the CPU for a longer time. Fixed quantums means that the CPU time within a quantum is the same for all applications (Though some applications can get more quantums than others).
 
 In WinNT4/Win2k/WinXP this setting can be configured at "Control Panel" -&gt; "Systerm Properties" -&gt; Advanced-tab -&gt; "Performance Options...".  
  
 The above setting reflects this DWORD value in the registry:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\PriorityControl\]  
>  Win32PrioritySeparation = 0

 For the WinNT4 there are the following values:
- 0 - Equal priority for all applications
- 1 - Medium priority to foreground application
- 2 - High priority to foreground application  
    
   More Info [MS KB232271](http://support.microsoft.com/kb/232271 "How to Optimize Windows NT Server Using the Registry [Q232271]")
 
 For the Win2k/WinXP the value set have been extended by using three 2 bits values: <table border="1"><tr align="center"><th>6-5 Bit</th><th>4-3 Bit</th><th>2-1 Bit</th><th>Result</th></tr><tr><td>10 (32)</td><td> </td><td> </td><td>Short Quantum</td></tr><tr><td>01 (16) </td><td> </td><td> </td><td>Long Quantum</td></tr><tr><td>00 (0) </td><td> </td><td> </td><td>Default (Prof.=Short, Srv.=Long)</td></tr><tr><td> </td><td>10 (8)</td><td> </td><td>Fixed Quantum for all</td></tr><tr><td> </td><td>01 (4) </td><td> </td><td>Variable Quantum for foreground</td></tr><tr><td> </td><td>00 (0) </td><td> </td><td>Default (Prof.=Variable, Srv.=Fixed)</td></tr><tr><td> </td><td> </td><td>10 (2)</td><td>High foreground boost/priority (3 times higher)</td></tr><tr><td> </td><td> </td><td>01 (1) </td><td>Medium foreground boost/priority (2 times higher)</td></tr><tr><td> </td><td> </td><td>00 (0) </td><td>No foreground boost/priority</td></tr></table>

 By adding each 2 bit value together you will get a value to use in the registry key. Examples:
- Optimize Performance for Applications: 32 + 4 + 2 = 38 and gives Short Quantum, Variable Quantum for foreground, High foreground boost.
- Optimize Performance for Background Services: 16 + 8 + 0 = 24 and gives Long Quantum, Fixed Quantum, No foreground boots.
 
 More Info [Inside Win2k](http://www.microsoft.com/mspress/books/sampchap/4354c.asp "Inside Microsoft Windows 2000, Third Edition")  
 More Info [MS Technet](http://www.microsoft.com/technet/prodtechnol/windows2000serv/reskit/regentry/29623.mspx "PriorityControl")  
  
 Related [Specify base priority when launching programs](/article/winnt-priority-programs.html)