---
title: 'Configue IDE ATA hard disk to use DMA transfer'
date: '2000-01-01T21:05:39+01:00'
status: publish
permalink: /article/winnt4-ide-dma.html
author: Snakefoot
excerpt: 'How to configure Windows NT4 to use DMA for IDE ATA hard drives.'
type: post
id: 368
category:
    - 'Tweak Performance'
tag:
    - ATA
    - dma
    - hard-disk-drive
    - IDE
    - PIO
post_format: []
tags:
    - 'IDE,hard-disk-drive,ATA,dma,PIO'
---
To get the best performance of your IDE hard disk, then one should make sure that [DMA transfer mode](/article/troubleshoot-hdd-dma.html) is enabled. Windows NT4 SP4 will automatically enable DMA transfer mode, but it might cause problems with drives, which doesn't support DMA transfers like old HDD and CD-ROM drives.  
  
 When DMA Transfer is enabled the following DWORD registry key is set:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\ATAPI \\Parameters \\DeviceX\]  
>  DriveParameter=0x1  
>   
>  Note the possible values are 0x1 (on - default), 0x0 (off), 0x2 (Forced on)

 More Info [MS KB191774](http://support.microsoft.com/kb/191774 "How to Obtain Dmacheck.exe for Windows NT [Q191774]") (Dmacheck.exe)  