---
title: 'Use process affinity to lock application to a single core'
date: '2010-01-21T02:31:13+01:00'
status: publish
permalink: /article/winnt-process-affinity.html
author: Snakefoot
excerpt: 'Applications optimized to run on single CPU systems, will perform worse on multi CPU systems.'
type: post
id: 826
category:
    - Tips
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - cpu
    - dos-emulator
    - process-scheduler
post_format: []
tags:
    - 'process-scheduler,dos-emulator,cpu'
---
Microsoft Windows NT has supported multiple CPU's from the beginning, and the process scheduler can switch the execution of applications from one CPU to another incase a CPU becomes overloaded. But many older applications are optimized for a single core operation and actually performs slower (or crashes) if Microsoft Windows is allowed to switch the application between CPU's.  
  
 The actual performance benefit from locking an old application to a single core is very minimal, so this advice is mostly for the old applications that actually crashes when run on a multi core computer. It can also be a possible solution if the timing in a game is a bit off, or there are sound delays.

##### Set process affinity using the Task Manager

 By launching the Task Manager (CTRL+SHIFT+ESC) then one can right-click any running process and choose "Set Affinity...". The change will last until the process stops, and will not be remembered the next time the process starts.  
  
 It is an easy way to check if an issue can be solved using process affinity. But some games might not handle the switch from fullscreen to Task Manager and back again without crashing.

##### Set process affinity using 3rd party application.

- [PsExec](http://technet.microsoft.com/en-us/sysinternals/bb897553.aspx) - Launches the application with the wanted process affinity.
- [StartAffinity](http://www.adsciengineering.com/StartAffinity/) - Works like PsExec.
- [THG Task Assignment Manager](http://www.tomshardware.com/reviews/bang-dual-processing-buck,815.html) - Detects when an application is launched and applies the wanted process affinity.
- [Core Affinity](http://coreaffinity.megabyet.net/) - Works like THG Task Assignment.
- [CPU Control](http://www.koma-code.de/index.php?option=com_content&task=view&id=88&Itemid=93) - Works like THG Task Assignment.
- [SMP Seesaw](http://www.mlin.net/SMPSeesaw.shtml) - Works on Windows NT4.

##### Set process affinity by modifying the executable

 imagecfg.exe is part of the [Microsoft support tools and resource kits](/article/winnt-resource-kit.html) and can modify an application to use the wanted process affinity.
 > imagecfg -a 0x1 c:\\folder\\myapp.exe

##### Set process affinity programmatically

- [SetThreadAffinityMask](http://msdn.microsoft.com/en-us/library/ms686247.aspx)
- [Process.ProcessorAffinity](http://msdn.microsoft.com/en-us/library/system.diagnostics.process.processoraffinity.aspx)

##### Locking the MSDOS subsystem to a single CPU

 Like all other processes the [MSDOS subsystem](/article/winnt-autoexec-config.html) can also be moved between CPU's. But where some applications can perform worse when between switched between CPU's, then it can actually cause the MSDOS subsystem to crash or lock entirely.  
  
 If going down the road of modifying the executable, then one will see that on Windows 2000/XP that ntvdm.exe is protected by [Windows File Protection](/article/winnt-wfp.html). The solution is to move the ntvdm.exe to another folder and modify this, and the change the registry to use the modified version:   
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\WOW\]  
>  CmdLine = "..."  
>  WowCmdLine = "..."

 Credits [Ask the Performance Team](http://blogs.technet.com/askperf/archive/2009/02/03/help-my-application-only-runs-on-a-single-processor-system.aspx)