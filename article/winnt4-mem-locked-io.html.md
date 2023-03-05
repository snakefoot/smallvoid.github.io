---
title: 'Configure the amount of memory that can be locked for I/O'
date: '2000-01-01T14:14:05+01:00'
status: publish
permalink: /article/winnt4-mem-locked-io.html
author: Snakefoot
excerpt: 'Improve the performance of high speed I/O devices by allowing them to lock more memory for data transfers.'
type: post
id: 28
category:
    - 'Tweak Performance'
tag: []
post_format: []
tags:
    - ''
---
There is a limit for how much memory the system can lock for I/O (Input/Output) operations. Increasing the limit might benefit applications or drivers, which are highly dependent on highspeed network or harddisk access, as it will allow a larger amount of outstanding I/O.  
  
 This DWORD value specifies how much memory (in bytes) that can be locked for I/O operations:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Session Manager \\Memory Management\]  
>  IoPageLockLimit=0 (0 = Calculated at boot, Default = 0)

 One can use the following chart for finding a value, though the best value is found by testing: <table border="1"><tr align="center"><th>Total RAM</th><th>IoPageLockLimit (Hex)</th><th>Locked RAM</th><th>Max value</th></tr><tr align="center"><td>64 MByte</td><td>0</td><td>Calculated</td><td>Total RAM minus 7 Byte</td></tr><tr align="center"><td>64-200 MByte</td><td>800000</td><td>2 MByte</td><td>Total RAM minus 16 MByte</td></tr><tr align="center"><td>256-500 MByte</td><td>1000000</td><td>4 MByte</td><td>Total RAM minus 16 MByte</td></tr><tr align="center"><td>512+ MByte</td><td>2000000</td><td>8 MByte</td><td>Total RAM minus 64 MByte</td></tr></table>

 Note Windows 2000 RTM (Without any service packs) also reacts to this registry key. If applying a service pack, then this registry setting doesn't have any affect.  
  
 More Info [MS KB102985](http://support.microsoft.com/kb/102985 "REG: CurrentControlSet Entries PART 2: SessionManager [Q102985]")  
 More Info [MS KB121965](http://support.microsoft.com/kb/121965 "HOWTO: Change Max Memory Allowed with MmProbeAndLockPages [Q121965]")  
  
 Credits [ArsTechnica.com](http://www.arstechnica.com/)