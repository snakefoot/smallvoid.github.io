---
title: 'Specify base priority when launching programs'
date: '2001-02-05T14:31:52+01:00'
status: publish
permalink: /article/winnt-priority-programs.html
author: Snakefoot
excerpt: 'Decide the CPU priority when starting an application.'
type: post
id: 30
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
WinNT is able to give different amount of CPU time to each program dependent on their priority. This can be used to launch an application (Like a Game) in high priority so other applications will have a hard time stealing the CPU time:

> Start "StartHigh" /HIGH C:\\Q3\\Quake3.exe

 It can also be used to launch certain background applications (SETI, Folding, Grid etc.) with low priority, so they cannot take CPU time from other applications.
 > Start "StartLow" /LOW C:\\Ud\_Agent\\Ud.exe

 To see the possible startup options run:
 > Start /?

 Besides using HIGH you can use these (Avoid RealTime if having only one CPU):  
<table border="1"><tr align="center"><th>Priority</th><th>Level</th></tr><tr><td>Realtime</td><td align="right">24</td></tr><tr><td>High</td><td align="right">13</td></tr><tr><td>Normal</td><td align="right">8</td></tr><tr><td>Low</td><td align="right">4</td></tr><tr><td>Abovenormal</td><td align="right">(Win2k+ only) 10</td></tr><tr><td>Belownormal</td><td align="right">(Win2k+ only) 6</td></tr></table>

 Note instead of making a batch file for every application to launch it with a certain priority, then one can send an application into a certain priority by creating a batch file High.bat with the following contents and save it in the SentTo-Folder:
 > Start "StartHigh" /High "%1"

 Note one can also add a new item "Start High Priority" to the context menu, so when right clicking an exe-file, one have the option to launch the exe-file with a certain priority.
> REGEDIT4  
>   
>  \[HKEY\_CLASSES\_ROOT\\exefile\\shell\\StartHigh\]  
>  @="Start &amp;High Priority"  
>   
>  \[HKEY\_CLASSES\_ROOT\\exefile\\shell\\StartHigh\\Command\]  
>  @="cmd.exe /c start \\"StartHigh\\" /High \\"%1\\""

 Note one can also change the priority right on the fly for a running application by using the Task Manager (CTRL+SHIFT+ESC).  
  
 More Info [MS KB103475](http://support.microsoft.com/kb/103475 "Starting Applications with /REALTIME May Hang Windows NT [Q103475]")  
 More Info [MS KB103810](http://support.microsoft.com/kb/103810 "Realtime Priority Applications And Windows NT [Q103810]")  
 More Info [MS KB106253](http://support.microsoft.com/kb/106253 "Program Priority and Multithreaded Applications [Q106253]")  
 More Info [MS KB191771](http://support.microsoft.com/kb/191771 "How to Alter a Program's Base Priority at a Command Prompt [Q191771]")  
  
 Related [Change your Processor quantums to tweak your applications](/article/winnt-process-scheduler-priority.html)  
  
 Credits [ntfaq.com](http://www.ntfaq.com/)