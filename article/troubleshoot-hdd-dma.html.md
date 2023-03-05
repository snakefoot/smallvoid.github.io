---
title: 'Diagnose performance issues with IDE ATA hard disk'
date: '2001-11-09T20:31:24+01:00'
status: publish
permalink: /article/troubleshoot-hdd-dma.html
author: Snakefoot
excerpt: 'Description of different causes and solutions to hard disk performance problems.'
type: post
id: 198
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - ATA
    - disk-performance
    - hard-disk-drive
    - IDE
post_format: []
tags:
    - 'hard-disk-drive,IDE,ATA,disk-performance'
---
The most important thing for good IDE hard disk performance is to enable DMA transfer. There are different interfaces available when attaching a hard disk, cdrom- or dvd-drive. The most simple interface is Programmed Input/Output (PIO), which provides good compatibility, but the PIO interface is a slow and it requires a lot of CPU time when accessing a hard disk. Direct Memory Access (DMA) is a fast interface, which isn't CPU bound but it requires that both the harddisk and motherboard supports DMA.  
  
 If the IDE hard disk is not connected properly then the operating system might revert back from DMA-mode to PIO-mode, which leads to very bad performance. Also some operating systems configures the IDE hard disk to use PIO-mode by default for compatibility reasons.  
  
 Go through the following check points for your Hard Disk Drive(HDD) :

- Check if DMA is enabled properly. If DMA is not enabled then moving and copying of files will cause high CPU usage. Even if DMA is enabled then it might be using a low level ATA, which causes it to block the tranfer rate the HDD is actually capable of. 
  - Check if the HDD supports the wanted ATA level.
  - Check if the HDD-Controller supports the wanted ATA level.
  - Check if the HDD-Cable supports the wanted ATA level.
  - Check if the drivers for the HDD-Controller supports the wanted ATA level (Also remember to install drivers for the HDD-Controller). 
      - [Configure DMA transfer in Windows 2000/XP](/article/winnt-ide-dma.html)
      - [Configure DMA transfer in Windows NT4](/article/winnt4-ide-dma.html)
      - [Configure DMA transfer in Windows 95/98/Me](/article/win9x-ide-dma.html)
- Check that you have attached the HDD properly. 
  - Try only to have one HDD on each HDD-Cable. Then the HDD won't have to share the channel with CD-ROM/DVD or other HDD. Since this will cause them to fight for the use of the channel blocking each other.
  - When having only one HDD on the HDD-Cable, make sure it is setup as Master.
  - Make sure the Master HDD is attached to the last terminator on the HDD-Cable and the Slave to the middle terminator on the HDD-Cable.
- Check that you are using a proper HDD-Cable which is not limiting the max transfer rate of the HDD (Do this by running HD Tach and see if the transfer rate is not constantly low, or has too many sudden drops in performance) 
  - If you want ATA 66 / 100 /133 then you need a 80 pin HDD-cable (Usually has blue terminators). Standard 40 pin HDD-Cables will only allow ATA 33.
  - Make sure if using 80 pin HDD-Cable that the Blue Terminator is attached to the HDD-Controller.
  - Make sure the HDD-Cable is not longer than 18 inches.
  - Make sure the HDD-Cable is not bad, and get another one if it is bad. A bad HDD-Cable can be caused by bad quality from the manufacturing or that the HDD-Cable is seriously bended. If the HDD-Cable is bad then the HDD and the HDD-Controller will negotiate a lower ATA level to avoid too many retransmissions. Thus blocking the max transfer rate of the HDD.
  - The optimal solution (For those who dare) is to get the shortest distance between HDD-Controller and the one HDD. To do this attach the HDD to the middle terminator and cut away the rest of the HDD-Cable along with the last terminator. If the last part is not cut away it will work like an antenna and cause disturbance in the HDD-Cable.
- Check if another PCI cards is conflicting with the HDD-Controller (Do this by running HD Tach without having TV-Out-, Sound- or Net-Adapter attached, and make sure that your HDD-Controller is not using the same IRQ as your display-adapter). If performance leap try to :  
  
  - Rearrange the PCI cards (Some cards are very sensitive).
  - Disable PnP OS in BIOS (BIOS will configure hardware instead of OS).
  - Make sure that no devices is sharing IRQ with the HDD-Controller (When the IRQs are shown by BIOS at bootup).
  - Assign static IRQ in BIOS for each slot instead of Auto (BIOS will not try to automatically configure the addon cards).
- Check if the HDD is attached to motherboard chipset controller that IDE Block mode is enabled in the motherboard BIOS. IDE Block Mode will increase transfer rate as it will copy blocks of up to 64K instead of a 512 Byte(single sector) at a time.
 
 Note many new hard disks are equipped with noise reduction features (Disc Drive Acoustics), which keeps the sound level down, but also reduces the performance of the hard disk. If noise is not an issue, then one can consider to disable the noise reduction using the disk configuration tool from the hard disk manufacture.