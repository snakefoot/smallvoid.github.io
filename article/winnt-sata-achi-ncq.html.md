---
title: 'Activate ACHI to enable Native Command Queuing'
date: '2010-01-18T00:30:22+01:00'
status: publish
permalink: /article/winnt-sata-achi-ncq.html
author: Snakefoot
excerpt: 'Native Command Queuing (NCQ) can improve hard disk performance, as it optimizes the order to execute read and write commands.'
type: post
id: 824
category:
    - Tips
    - 'Tweak Performance'
tag:
    - disk-performance
    - hard-disk-drive
    - sata
    - SMART
post_format: []
tags:
    - 'sata,disk-performance,SMART'
---
Motherboards with onboard SATA controllers are by default configured to run in SATA mode (with legacy support). This gives the best compatiblity as it allows operating systems without SATA support to install and operate.  
  
[Advanced Host Controller Interface (AHCI)](http://en.wikipedia.org/wiki/Advanced_Host_Controller_Interface) enables support for hot-plugging and [native command queuing](http://en.wikipedia.org/wiki/Native_Command_Queuing), but only the newest operating systems supports this interface. Therefore one have enable it explicitly in the motherboard BIOS.  
  
 If already having installed Windows Vista/7 without ACHI enabled, then Windows has automatically disabled its AHCI driver to improve the boot time (not loading unnecessary harddisk controller drivers). Therefore one have to activate the AHCI driver before enabling ACHI support in the motherboard BIOS. Open the registry editor and set the following DWORD value:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Msahci\]  
>  Start = 0

 Note if changing to AHCI mode in motherboard BIOS and the Windows operating system doesn't have a AHCI enabled driver, then it will give a blue screen of death (BSOD) with STOP 0x0000007B INACCESSABLE\_BOOT\_DEVICE.  
  
 Note it can be a good idea to get the latest AHCI driver from the motherboard chipset manufacture, instead of using the default AHCI driver included with Microsoft Windows.  
  
 Note enabling AHCI might stop [SMART](http://en.wikipedia.org/wiki/S.M.A.R.T.) data from working. This is apparently a driver issue, and doesn't happen if using Microsoft Windows default driver.  
  
 More Info [MS KB922976](http://support.microsoft.com/kb/922976 "Error message when you change the SATA mode of the boot drive: "STOP 0x0000007B INACCESSABLE_BOOT_DEVICE"")