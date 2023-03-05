---
title: 'Configue IDE ATA hard disk to use DMA transfer'
date: '2000-06-06T23:24:52+02:00'
status: publish
permalink: /article/winnt-ide-dma.html
author: Snakefoot
excerpt: 'How to configure Windows to use DMA for IDE ATA hard drives.'
type: post
id: 372
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - ATA
    - disk-performance
    - dma
    - hard-disk-drive
    - IDE
    - PIO
post_format: []
tags:
    - 'PIO,dma,IDE,ATA,hard-disk-drive,disk-performance'
---
To get the best performance of your IDE hard disk, then one should make sure that [DMA transfer mode](/article/troubleshoot-hdd-dma.html) is enabled.  
  
 To configure the DMA-mode used for your IDE devices attached to the onboard controller:

1. Open Control Panel and double-click System.
2. Select the Hardware-tab and click Device Manager.
3. Find the IDE ATA/ATAPI Controllers and double-click either primary or secondary IDE channel depending on which your IDE devices are attached.
4. The following options should be available in Advanced Settings: 
  - DMA if available
  - PIO only
 
 Note that if DMA is enabled for a device which doesn't support it then this can cause data corruption.  
  
 Note that some ATAPI devices like CD-ROM, Tape-Drive, MO-Drive is set to PIO by default, so one manually has to enable DMA as described in the beginning.  
  
 Note if more than 6 transfer timeouts occurs then Windows tries to degrade the DMA mode to a lower level to prevent data errors (Independent of lifetime). If the transfer timeouts continues to occur then it will change to PIO mode for the IDE device. The only way to reenable DMA is to remove the device or controller in the Device Manager (It will redetect the device automatically). More Info [MS KB817472](http://support.microsoft.com/kb/817472 "IDE ATA and ATAPI disks use PIO mode after multiple time-out or CRC errors occur [Q817472]").  
  
 Note with Windows XP SP2 and Windows 2000 SP3 a less aggressive policy was introduced, so instead of remembering all DMA transfer timeouts throughout history, then it would reset the timeout counter if a succesful transfer was performed. This policy is not enabled by default, but can enabled with the following DWORD registry key:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Class \\{4D36E96A-E325-11CE-BFC1-08002BE10318}\\000**X**\]  
>  ResetErrorCountersOnSuccess = 1  
>   
>  Where **X** is a number from 1 to 9 (Depending on how many onboard IDE controllers there is in the system).

 Note Win2k/Xp/2k3 without any service pack applied will only use UDMA33 on Intel onboard standard IDE-Controller. This can be upgraded to UDMA66 by adding/updating this DWORD value:
> \[HKEY\_LOCAL\_MACHINE\\ System\\ CurrentControlSet\\ Control\\ Class\\ {4D36E96A-E325-11CE-BFC1-08002BE10318}\\ 0000\]  
>  EnableUDMA66=1  
>   
>  More Info [MS KB247951](http://support.microsoft.com/kb/247951 "HOWTO: Enable UDMA66 Mode on Intel Chipsets [Q247951]")

 More Info [MS Technet](http://www.microsoft.com/whdc/hwdev/tech/storage/IDE-DMA.mspx "DMA Mode for ATA/ATAPI Devices in Windows XP")  
 More Info [MS KB260233](http://support.microsoft.com/kb/260233 "Support for ATA100 (Mode 5 ) in Windows 2000 [Q260233]") (ATA 100 is supported in Win2k SP2)  