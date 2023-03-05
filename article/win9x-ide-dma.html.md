---
title: 'Configure IDE ATA hard disk to use DMA transfer'
date: '2000-01-01T18:30:08+01:00'
status: publish
permalink: /article/win9x-ide-dma.html
author: Snakefoot
excerpt: 'How to configure Windows 9x to use DMA for IDE ATA hard drives.'
type: post
id: 87
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - ATA
    - cpu
    - disk-performance
    - dma
    - hard-disk-drive
    - IDE
    - PIO
post_format: []
tags:
    - 'IDE,ATA,PIO,dma,cpu,hard-disk-drive,disk-performance'
---
To get the best performance of your IDE hard disk, then one should make sure that [DMA transfer mode](/article/troubleshoot-hdd-dma.html) is enabled. Windows 98 uses by default PIO-mode which is much slower than DMA mode.  
  
 In Win95b+ and Win98 you can check if DMA is enabled by going to the Control Panel -&gt; System -&gt; Device Manager -&gt; Disk Drives -&gt; "Your HDD" -&gt; Settings and see if the DMA checkbox is set. This change is reflected here in the registry:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Class \\hdc \\XXXX\]  
>  IDEDMADRIVEx=01  
>   
>  More Info [MS KB258757](http://support.microsoft.com/kb/258757 "How to Enable Direct Memory Access (DMA) [Q258757]")

 In Win95b+ and Win98 a small fix can be applied to the builtin IDE drivers, so DMA is automatically enabled for new IDE-Device. Edit the file Windows\\Inf\\Mshdc.inf and add the lines in **bold** if they are not already there:
> \[ESDI\_AddReg\]  
>  HKR,,DriverDesc,,"ESDI Port Driver"  
>  HKR,,DevLoader,,\*IOS  
>  HKR,,PortDriver,,ESDI\_506.pdr  
> **HKR,,IDEDMADrive0,3,01**  
> **HKR,,IDEDMADrive1,3,01**  
> **HKR,,IDEDMADrive2,3,01**  
> **HKR,,IDEDMADrive3,3,01**

 Add the same bold lines to the file Windows\\Inf\\Diskdrv.inf in the section \[DiskReg\]. If the system is already setup, then one manually have to remove all IDE devices in the Device Manager and reboot to get all devices redetected with DMA enabled.  
  
 Note that the above settings is only valid if using the builtin IDE drivers supplied with Win9x. If using 3rd party drivers for the IDE Controller, then DMA should be enabled automatically, and the drivers will not react to the changes made for the builtin IDE drivers.  
  
 More Info [MS HWDEV: Enabling IDE DMA on Windows-based Systems](http://www.microsoft.com/whdc/archive/idedma.mspx)  
 More Info [MS KB159560](http://support.microsoft.com/kb/159560 "DMA Check Box Does Not Remain Checked [Q159560]")  
 More Info [MS KB171353](http://support.microsoft.com/kb/171353 "Computer with Ultra DMA IDE Controller May Hang [Q171353]")  
 More Info [MS KB193473](http://support.microsoft.com/kb/193473 "Computer with IDE DMA Hard Disk Hangs When Resumed [Q193473]")  
 More Info [MS KB229085](http://support.microsoft.com/kb/229085 "Drive Does Not Have a DMA Check Box [Q229085]")  
 More Info [MS KB235859](http://support.microsoft.com/kb/235859 "DMA CD-ROM Drive Icon Does Not Appear in Windows Explorer [Q235859]")  