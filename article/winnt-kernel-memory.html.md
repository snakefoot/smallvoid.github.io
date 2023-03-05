---
title: 'Description of the kernel memory area in Windows NT'
date: '2006-02-23T19:06:30+01:00'
status: publish
permalink: /article/winnt-kernel-memory.html
author: Snakefoot
excerpt: 'How the kernel memory area is divided into the different page pools.'
type: post
id: 264
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - kernel
    - memory-manager
    - page-pool
post_format: []
tags:
    - 'kernel,page-pool,memory-manager'
---
The 32 bit Windows can address 4 GB memory, which for each process it divided into a 2 GB user area and a 2 GB kernel area. The 2 GB kernel area is shared between all the processes. These two areas are also called virtual user address range and virtual system address range.  
  
 The kernel area is used to contain all system data structures and information. During the Windows startup the NT Executive allocates the kernel area and divides it into smaller areas.

- Address tables for accessing physical memory and mapping to [virtual memory](/article/windows-page-file.html). Like the Page Frame Number (PFN) list that keeps track of all the physical memory pages an their state (Is it in use ? Who uses it ? How many time has it been used ? etc.).
- Memory pools for drivers to allocate buffers (paged and non-paged)
- Page Table Entries (PTE) for addressing system resources like processes / threads / files / connections / IO-buffers.
- [File System Cache](/article/winnt-system-cache.html)
 
 The maximum size of the areas are fixed and depends on available physical memory. The fixed size makes it possible for an area to become depleted even though there is plenty of memory in the kernel area. If this happens, then it can either cause very low performance or that the machine crashes. Windows Vista changes this by making the areas dynamic.  
  
 Even if the maximum size is fixed, then the actual size of the different areas can grow and shrink depending on the load. If there is a lot of file activity then the file cache will grow, leaving less memory available for paged pool allocations. And if the paged pool allocations gets close to its maximum size, then the memory manager will start trimming by reclaiming memory from the file-cache and [paging to disk](/article/windows-page-file.html), to make sure there is enough available RAM to handle the extra load. More Info [MS KB312362](http://support.microsoft.com/kb/312362 "Server is unable to allocate memory from the system paged pool"), [MS KB304101](http://support.microsoft.com/kb/304101 "Backup program is unsuccessful when you back up a large system volume [Q304101]")  
  
 Use the Windows Task Manager to see the size of paged and non-paged memory pools. Another way is to use [Perfmon](/article/winnt-services-sysmonlog.html) and Add Counters... from the [Memory](http://msdn.microsoft.com/library/en-us/wmisdk/wmi/win32_perfrawdata_perfos_memory.asp "Win32_PerfRawData_PerfOS_Memory") Performance Object (\*Hint\* notice the Explain-button):
- Cache Bytes Peak
- Free System Page Table Entries
- Pool Nonpaged Allocs
- Pool Nonpaged Bytes
- Pool Paged Allocs
- Pool Paged Bytes
 
 Change how Windows calculates paged-pool size (Can improve driver performance):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager \\Memory Management\]  
>  PagedPoolSize = 0 (Default = 0, Max = 0xFFFFFFFF, Calculated = 0)  
>   
>  Note if wanting a minimum value to give better room for PTE or System File Cache, then specify a value of 192000000 (192 MByte).  
>   
>  Note the max paged-pool size is 650 MByte for Win2k3 (470 MByte for Win2k/WinXP, 192 MByte for WinNT4), and 256 MByte for the non-paged-pool (128 MByte for WinNT4). Independent of the amount of physical memory.  
>   
>  More Info [MS KB177415](http://support.microsoft.com/kb/177415 "How to Use Memory Pool Monitor (Poolmon.exe) to Troubleshoot Kernel Mode Memory Leaks [Q177415]")  
>  More Info [MS KB304101](http://support.microsoft.com/kb/304101 "Backup program is unsuccessful when you back up a large system volume [Q304101]")  
>  More Info [MS KB312362](http://support.microsoft.com/kb/312362 "Server Is Unable to Allocate Memory from the System Paged Pool [Q312362]")

 Change how Windows calculates Page Table Entries (Can allow addressing of large video memory areas):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager \\Memory Management\]  
>  SystemPages = 0 (Default = 0, Max = 0xFFFFFFFF, Calculated = 0)  
>   
>  Note if wanting a minimum value to give better room for paged-pool or System File Cache, then use the default value of 0.  
>   
>  Note the max PTE size is 1.3 GByte for Win2k3/WinXP (470 Mbyte for Win2k, 192 MByte for WinNT4). Independent of the amount of physical memory.  
>   
>  More Info [MS KB189327](http://support.microsoft.com/kb/189327 "How To Map Adapter RAM into Process Address Space [Q189327]")  
>  More Info [MS KB247904](http://support.microsoft.com/kb/247904 "How to Configure the Paged Address Pool and System Page Table Entry Memory Areas [Q247904]")  
>  More Info [MS KB256004](http://support.microsoft.com/kb/256004 "How to troubleshoot "STOP 0x0000003F" and "STOP 0x000000D8" error messages [Q256004]")  
>  More Info [MS KB313707](http://support.microsoft.com/kb/313707 "XADM: An Exchange 2000 Server with the "/3GB" Switch in the Boot.ini File May Lose Network Connectivity Under a Heavy Messaging Load [Q313707]")  
>  More Info [MS KB818894](http://support.microsoft.com/kb/818894 "Changes to increase the number of open files in Windows 2000, in Windows 2003, and in Windows XP [Q818894]")

 Note there exists a [BOOT.INI](/article/winnt-boot-ini.html) setting [/3GB](/article/winnt-boot-ini.html#BOOT_INI_3GB), which enables 4GT RAM tuning. Changing how Windows divides the 4 GB, so the user area gets 3 GB and the kernel area only gets 1 GB. This can be useful when using [large address aware](http://msdn2.microsoft.com/en-us/library/bb147385.aspx "64-bit programming for Game Developers") applications, which supports more than 2 GB memory (Ex. [MS Exchange](http://support.microsoft.com/kb/815372)/[SQL Server](http://msdn2.microsoft.com/en-US/library/aa175282(sql.80).aspx "Inside SQL Server 2000's Memory Management Facilities")). Naturally this setting puts a strain on the available kernel resources, so one have to be careful with it. Windows 2003 introduces an extra BOOT.INI setting [/USERVA](/article/winnt-boot-ini.html#BOOT_INI_USERVA), which allows one to better configure the boundary between the kernel- and user-memory area.  
  
 Note the registry size limit (RSL) or maximum registry size is by default limited to 25% of the pagepool size, but can be increased to 80% (RegistrySizeLimit). More Info [MS KB124594](http://support.microsoft.com/kb/124594 "Understanding and configuring Registry Size Limit (RSL) [Q124594]").  
 If changing the RSL through the user interface, and specifies a value that requires a larger paged-pool size, then it will modify the values of PagedPoolSize and SystemPages, which can lead to undesirable behavior. More Info [MS KB166840](http://support.microsoft.com/kb/166840 "Err Msg: Not Enough Storage to Complete Operation [Q166840]").  
 The registry size limitation has been removed with Windows XP/2003. More Info [MS KB292726](http://support.microsoft.com/kb/292726 "Registry Size Limit functionality has been removed from Windows Server 2003 and from Windows XP [Q292726]").  
 The size of system registry hive is still limited (16 MB for Win2k/32 MB for Win2k3) by the memory available to the startup proces. More Info [MS KB302594](http://support.microsoft.com/kb/302594 "The system hive memory limitation is improved in Windows Server 2003 [Q302594]")  
  
 Note if wanting to access more than 4 GB RAM on 32 bit Windows then [PAE](/article/winnt-boot-ini.html#BOOT_INI_PAE) must be activated, which requires that the CPU hardware has 36 bit memory registers (instead of 32 bit) so it can address up to 64 GByte of RAM. The Windows address tables becomes 64 bit wide (8 bytes instead of 4 bytes each) and requires more kernel memory to hold the memory page address table. PAE will still serve 32 bit addresses to the applications, so it is possible to run multiple applications (or virtual machines) without running out of available physical RAM. If an application wants to access more than 2 GByte memory, then it should use the [Address Windowing Extensions](http://msdn2.microsoft.com/en-us/library/aa366527.aspx) (AWE) API to access the extra memory available through PAE. More Info [AWE Performance](http://msdn.microsoft.com/en-us/library/ms810461.aspx "Address Windowing Extensions and Microsoft Windows 2000 Datacenter Server")  
  
 Note if wanting a lot of kernel memory in 32 bit Windows, then one should not install more than 4 GByte RAM in the computer. Because the kernel is limited to only 2 GByte independent of physical memory, and when adding more RAM, then it will use kernel memory for mapping the extra RAM to virtual memory.  
  
 Note some motherboards reserves the upper part of the 32 bit address space for system BIOS and PCI devices. Therefore if having 4 GB RAM (or more) installed, then one might loose 1 GB of memory because it has been reserved, so the operating system only sees 3 GB RAM. Some motherboards solves this issue by having a BIOS option that allows remapping of the reserved memory area above the 4 GB boundary, also called "memory hole". Because some device drivers doesn't support remapping of the reserved memory area, then XP SP2 disables the remapping to improve driver compatibility. More Info [MS KB888137](http://support.microsoft.com/kb/888137 "The amount of RAM reported by the System Properties dialog box and the System Information tool is less than you expect after you install Windows XP Service Pack 2"), [MS KB888137](http://support.microsoft.com/kb/929605 "The system memory that is reported in the System Information dialog box in Windows Vista is less than you expect if 4 GB of RAM is installed")  
  
 More Info [MS Technet](http://www.microsoft.com/downloads/details.aspx?familyid=ed0e8084-abf7-4c00-ba6a-7d658cdb052a "Detection, Analysis, and Corrective Actions for Low Page Table Entry Issues") (Excellent article about managing kernel memory)  
 More Info [MSDN](http://msdn.microsoft.com/library/en-us/dngenlib/html/msdn_ntvmm.asp) (The Virtual-Memory Manager in Windows NT)  
 More Info [MSDN - Memory Limits of each Windows version](http://msdn2.microsoft.com/en-us/library/aa366778.aspx)  
  
 Credits [MusikBanken.se](http://www.musikbanken.se/gigastudio/)