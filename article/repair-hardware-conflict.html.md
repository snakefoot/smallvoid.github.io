---
title: 'Checkpoints for fixing hardware conflicts'
date: '2002-08-14T20:00:40+02:00'
status: publish
permalink: /article/repair-hardware-conflict.html
author: Snakefoot
excerpt: 'Steps for finding what hardware devices that is causing problems.'
type: post
id: 267
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - drivers
    - event-log
    - hardware
    - system-recovery
post_format: []
tags:
    - 'hardware,drivers,event-log,system-recovery'
---
If the computer crashes, reboots, restarts, freezes, hangs, acts slow or is jerky, try the following checkpoints one by one to see if it makes the software/hardware problem go away:

- If using WinNT4/Win2k/WinXP then check the System and Application [Event Log](/article/winnt-services-eventlog.html) for entries that describes failures. If such entries exists use the Event ID to investigate the possible causes of these failures.
- If using WinNT4/Win2k/WinXP and experiencing Blue Screen of Death (BSOD), then activate "Kernel Memory Dump" and try to use [WinDbg](/article/winnt-windbg.html) to examine the crash dump for possible sinners.
- Check if you have enough free space (100 MByte or so) on your system drive for swap file etc.
- Perform a thorough disk scanning of your harddrives (Perform a backup of vital data first) 
  - Win9x/Me : [Scandisk](http://support.microsoft.com/kb/186365 "Description of ScanDisk for Windows (Scandskw.exe) in Windows 98/Me [Q186365]")
  - Win2k/XP : [Chkdsk /r](http://support.microsoft.com/kb/315265 "How to perform disk error checking in Windows XP [Q315265]")
- Check the Win2k/WinXP system files using the [System File Checker](/article/winnt-sfc.html).
- Check if the problem is related to a [Broken Internet Explorer](/article/repair-internet-explorer.html) (Check for virus / trojans / spyware / malware / adware / rootkits / etc.)
- Check if having [Enabled sound and graphics acceleration properly](/article/windows-update-directx.html)
- Check if having configured [IDE HDD for optimal DMA mode](/article/troubleshoot-hdd-dma.html)
- If the problem arose over time, then try to rollback: Changes in Motherboard BIOS, Changed hardware, Installed Applications, Installed drivers etc.
- Flash motherboard BIOS with the newest release from manufacture
- Update [drivers for all your devices](/article/windows-update-drivers.html) (Motherboard Chipset, Sound card, Network Card, Display Adapter, HDD-Controller etc.). Avoid using BETA drivers but go for official WHQL certified drivers instead.
- [Update Windows](http://corporate.windowsupdate.microsoft.com/) with the newest patches from Microsoft
- Clean the computer from old ghost/phantom devices: 
  - Win9x/Me [Boot in safemode to remove old ghost devices](/article/win9x-ghost-devices.html)
  - Win2k/XP [Uninstall ghost devices or services](/article/winnt-ghost-devices.html)
- Uninstall any 3rd party background applications like firewall or antivirus (Or make a clean install of Windows). Some 3rd party tools make hooks into the system and if a tool breaks then it can break the entire system.
- If the problems only occur with a single application, then it might be a good idea to visit forums at the official homepage or at fan sites and see if others are having similar problems (And maybe a solution).
 
 Hardware Checkpoints:
- Check that you are not overclocking CPU, RAM, Bus, Display Adapter, etc. and if so then set back to normal speed
- Check for CPU and GPU heat problems using [MBM](http://mbm.livewiredev.com/) or similar. Motherboard-temperature should stay around 30 celsius. GPU and CPU-temperature should stay below 70 celsius. If the temperature is too high it can easily cause disturbance on the display adapter or cause instability.
- Check memory configuration: 
  - Using memory modules of different brand or speed may cause instability
  - Using memory timings (Motherboard BIOS) which are too harsh may cause instability
  - Using memory bus speeds (Motherboard BIOS) which are off sync with Front Side Bus may cause instability
  - Use [Memtest86.com](http://www.memtest86.com/) to diagnose faults within installed memory
- Load Motherboard BIOS defaults.
- Check that the motherboard BIOS option "PnP OS" is set to "No"
- Unplug your USB devices and if possible put converters on keyboard and mouse to use PS/2
- Disable any unneeded onboard devices (COM1, COM2, LPT1, USB, Onboard IDE, Onboard Sound, etc.) in your motherboard BIOS
- Check for IRQ conflicts by looking in the motherboard manual for which PCI slots that are sharing the same IRQ (Can also share IRQ with onboard devices). Make sure that highspeed devices like Display Adapter, Sound Card and IDE/SCSI Controller are not sharing IRQ with other devices. After BIOS POST and before operating system starts loading then usually a listing is shown of IRQ's and their assignment. 
  - Usually one can use IRQ steering within the motherboard BIOS to configure IRQ assignment to PCI slots
  - Usually when two PCI slots are sharing the same IRQ, then one should use them for low speed devices or only one high speed device
  - Usually one shouldn't use the PCI slot next to the AGP port (Display Adapter) as the two devices will share the same IRQ
- Assign a static free IRQ for each PCI slot in the motherboard BIOS
- Take out all PCI cards except the Display Adapter. (To narrow down the problem area)
- Take out all the memory modules except one, and maybe try to move the one memory module to a different slot
- Try a different Power Supply Unit (PSU), preferable a 300-350 W, as the CPU and display adapter might require more power.