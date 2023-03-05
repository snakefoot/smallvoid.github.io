---
title: 'Changing hardware abstraction layer in Windows 2000 / XP'
date: '2001-01-15T19:29:55+01:00'
status: publish
permalink: /article/winnt-hardware-abstraction-layer.html
author: Snakefoot
excerpt: 'Windows NT hardware abstraction layer can be changed if the motherboard doesn''t support the one chosen by default.'
type: post
id: 266
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - acpi
    - hardware-abstraction-layer
    - standard-pc
post_format: []
tags:
    - 'acpi,standard-pc,hardware-abstraction-layer'
---
Windows NT is able to use different Hardware Abstraction Layers (HAL). Two of them is Standard PC and ACPI PC, which has different ways of performing hardware resource management:

- ACPI PC 
  - Completely PnP and handles the configuration of your devices(PnP) and gives you no control. It can solve most resource conflicts. If a [conflict](/article/repair-hardware-conflict.html) happens then it has be fixed in BIOS or changing addon cards.
  - Includes power management, so if having a laptop it will help on battery time
  - Doesn't show the actual hardware IRQ's the different devices uses, instead it has one of these behaviors: 
      - It looks like all devices are sharing the same IRQ, but it just means they are controlled by the same ACPI Controller
      - It looks like all devices have their own IRQ, but assigned IRQ is an software IRQ (&gt;15)
- Standard PC 
  - Includes some Plug'n'Play (PnP) but still allow you to configure your devices. There is a higher chance of resource conflict, but you might be able to solve it in Windows before going into BIOS.
  - Limited power management features, and for some motherboards it gives better performance and less conflicts
  - Will show the actual hardware IRQ's the different devices are using
 
 It is possible to change from ACPI to Standard PC after having installed Windows, though some reports problems doing this. It is recommended to make a backup of your current "Hardware Profile" before applying this:
1. Go to "System Properties" in Control Panel
2. Select the tab "Hardware" (Press the button "Hardware Profiles" to make a backup before continuing)
3. Press the button "Device Manager" (Will bring forth a tree)
4. Find the node "Computer" and expand
5. You should now see a component called "Advanced Configuration and Power Interface (ACPI) PC"
6. View component properties (Double click the component)
7. Select the tab "Driver"
8. Press the button "Update Driver..."
9. Select the option "Display list of the known drivers..."
10. It will now show the current driver for the component
11. Select the option "Show all hardware of this device class"
12. It will now show different types of computers
13. Select the driver "Standard PC"
14. It will now redetect all your hardware
 
 Note one can also use the change of Computer Driver, when upgrading to a dual processor thus having multiple CPUs (Or just enabling Intel HyperThreading (HT)). More Info [MS KB234558](http://support.microsoft.com/kb/234558 "HOW TO: Add Support for Multiple Processors in Windows 2000 [Q234558]").  
  
 Note it is possible to specify what HAL Windows should use during the install, instead changing HAL after the install, and is most likely the best way:  
- One way is to edit the file "C:\\Txtsetup.sif"(It is made during the textual part of the install process) by setting:
  > \[ACPIOptions\]  
  >  ACPIEnable = 0 (Disabled = 0, Enabled if ACPI BIOS = 1, Enabled if certified ACPI BIOS = 2, Default = 2)
- Another way is to Press F7 when Win2k install says "Press F6 if you need to install a third party SCSI or RAID driver". It will not give any confirmation of that you pressed F7, but it will not use ACPI.
- Yet another way is to press F5 instead of F7. This will bring forth a menu where it is possible to select from a whole range (Might have to press arrow-up/down to see them all): <table border="1"><tr><th>HAL</th><th>File</th><th>Description</th></tr><tr><td>Standard PC</td><td>Hal.dll</td><td>Any Standard PC, non-ACPI and non-MPS (Usually 386, 486, Pentium, Pentium II, or Pentium III)</td></tr><tr><td>ACPI PC</td><td>Halacpi.dll</td><td>Applies to a single processor motherboard with single processor (Pentium 4, Athlon)</td></tr><tr><td>ACPI Multiprocessor PC</td><td>Halmacpi.dll</td><td>Applies to a multiple-processor ACPI computer.</td></tr><tr><td>ACPI Uniprocessor PC</td><td>Halaacpi.dll</td><td>Applies to an ACPI multiple-processor board but with a single processor installed.</td></tr><tr><td>MPS Multiprocessor</td><td>Halmps.dll</td><td>Applies to non-ACPI computers with a dual processor running.</td></tr><tr><td>MPS Uniprocessor</td><td>Halapic.dll</td><td>Applies to non-ACPI computers dual processor motherboard with a single processor installed.</td></tr></table>
 
 More Info [MS KB216251](http://support.microsoft.com/kb/216251 "HOW TO: Specify a Specific or Third-Party HAL During Windows Setup [Q216251]")  
 More Info [MS KB216573](http://support.microsoft.com/kb/216573 "How Windows Determines ACPI Compatibility [Q216573]")  
 More Info [MS KB224826](http://support.microsoft.com/kb/224826 "Troubleshooting Text-Mode Setup Problems on ACPI Computers [Q224826]")  
 More Info [MS KB234558](http://support.microsoft.com/kb/234558 "HOW TO: Add Support for Multiple Processors in Windows 2000 [Q234558]")  
 More Info [MS KB237556](http://support.microsoft.com/kb/237556 "How to Troubleshoot Windows 2000 Hardware Abstraction Layer Issues [Q237556]")  
 More Info [MS KB243883](http://support.microsoft.com/kb/243883 "Windows 2000 Loses Date and Time on Every Boot [Q243883]")  
 More Info [MS KB252420](http://support.microsoft.com/kb/252420 "General Description of IRQ Sharing in Windows 2000 [Q252420]")  
 More Info [MS KB295116](http://support.microsoft.com/kb/295116 "A Description of the Windows XP Setup Function Keys [Q295116]")  
 More Info [MS KB299340](http://support.microsoft.com/kb/299340 "How to force a Hardware Abstraction Layer during an upgrade or an installation of Windows XP [Q299340]")  
 More Info [MS KB309283](http://support.microsoft.com/kb/309283 "HAL options after Windows XP or Windows Server 2003 Setup [Q309283]")  