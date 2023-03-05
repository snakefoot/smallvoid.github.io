---
title: 'Restore boot manager when it is missing or compressed'
date: '2007-10-30T01:03:54+01:00'
status: publish
permalink: /article/winnt-bootmgr-missing.html
author: Snakefoot
excerpt: 'Windows Vista will fail to boot if it cannot find the files used to load the boot manager.'
type: post
id: 754
category:
    - Troubleshoot
    - Troubleshoot
tag:
    - boot-manager
    - system-recovery
post_format: []
tags:
    - 'boot-manager,system-recovery'
---
Windows Vista includes a new Boot Manager (BootMgr) that replaces the old [NT Loader](/article/winnt-update-boot-manager.html) (Ntldr).  
  
 If you don't have the install DVD, then go ask friends/family/work whether they have a disc you can borrow. If your computer cannot boot from a DVD, then you can use another computer to [Create a Windows Vista/7 Recovery disk on an USB stick](/article/windows-usb-boot.html).

##### Boot Manager is missing

 If the boot partition no longer can be found, then Vista will display the following error:
> BOOTMGR is missing. Press Ctrl+Alt+Del to restart  
>   
>  The Windows Boot Configuration Data file is missing required information  
>   
>  More Info [MS KB919529](http://support.microsoft.com/kb/927391 "Windows Vista no longer starts after you install an earlier version of the Windows operating system in a dual-boot configuration")  
>  More Info [MS KB927391](http://support.microsoft.com/kb/927391 "Error message when you start Windows Vista: "The Windows Boot Configuration Data file is missing required information"")  
>  More Info [MS KB2622803](http://support.microsoft.com/kb/2622803 "You receive Error message: "Bootmgr is missing Press Ctrl+Alt+Del to restart" when starting Windows")

 Check points for fixing missing boot-manager:
- Check that your [boot device is configured properly](/article/no-boot-device-found.html)
- Boot into [Windows Recovery Environment](/article/winnt-recovery-environment.html) (WinRE) and perform a "Startup Repair".
- If that also fails then boot into WinRE again, and go to the "Command Prompt" and execute this command:
  > Bootrec.exe /RebuildBcd

##### Boot Manager is compressed

 If by accident having compressed the entire boot partition, then Vista will display the following error:
 > BOOTMGR is compressed. Press Ctrl+Alt+Del to restart

 Check points for fixing compressed boot-manager:
- Boot into [Windows Recovery Environment](/article/winnt-recovery-environment.html) (WinRE) and perform a "Startup Repair".
- If the above doesn't solve the problem then boot into WinRE again, but when selecting the Vista-installation, then press "Load Drivers" (Instead of "Next") and use the mini Windows Explorer to right-click the boot-drive and deselect "Compress this Drive" and choose Apply to sub-folders and files.
- If that also fails then boot into WinRE again, and go to the "Command Prompt" and execute these commands: 
  > compact /U C:\\bootmgr
  > compact /U C:\\ntldr
- If you for some strange reason have lost your Vista DVD, then you can also use a Windows 2000 / XP install CD and enter the [recovery console](/article/winnt-recovery-console.html) instead and execute the following commands: 
  > attrib -c c:\\bootmgr
  > attrib -c c:\\ntldr