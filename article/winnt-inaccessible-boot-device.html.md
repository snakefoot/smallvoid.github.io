---
title: 'Fix blue screen of death with INACCESSIBLE_BOOT_DEVICE'
date: '2003-08-16T22:34:40+02:00'
status: publish
permalink: /article/winnt-inaccessible-boot-device.html
author: Snakefoot
excerpt: 'Description of the different situations where Windows NT can fail to boot because it no longer can find the boot device.'
type: post
id: 463
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - blue-screen-of-death
    - boot-manager
    - system-recovery
    - windows-install
post_format: []
tags:
    - 'blue-screen-of-death,system-recovery,windows-install,boot-manager'
---
Windows NT is very sensitive about changes in the boot devices (compared to Win9x), and the slightest change can cause a Blue Screen Of Death (BSOD) with stop code INACCESSABLE\_BOOT\_DEVICE (0x0000007B). There are different situations which can cause this BSOD:

- **When installing Windows NT:**  
   This is usually because the HDD is attached to a controller which not natively supported by Windows NT.  
   During the installation of Windows NT it says "Press F6 if you need to install a third party SCSI or RAID driver" at this point press F6 and have the drivers for your HDD-Controller ready on a floppy disk.  
    
   Note even if having supplied the right drivers, then it is possible for Windows to get confused, so it tries to use its own included drivers when booting after the text-mode install (Causing BSOD). This might be solved by moving the HDD-controller in question to another PCI-slot right after getting the BSOD, and the supplied drivers should adapt to the new PCI-slot.  
    
   More Info [MS KB220845](http://support.microsoft.com/kb/220845 "Adding Third-Party or Updated Driver During Windows Setup [Q220845]")  
   More Info [MS KB295116](http://support.microsoft.com/kb/295116 "A Description of the Windows XP Setup Function Keys [Q295116]")  
   More Info [MS KB314859](http://support.microsoft.com/kb/314859 "Limited OEM Driver Support Is Available with F6 During Windows XP Setup [Q314859]")  
   More Info [MS KB822051](http://support.microsoft.com/kb/822051 "How to troubleshoot "Stop 0x0000007B" error messages that occur when you run Windows 2000 Setup [Q822051]") (Replaces MS KB271274)  
    
   Related [Include 3rd party controller drivers using unattended install](/article/recovery-console-drivers.html)
- **When moving an existing Windows NT install to different hardware:**  
   One can only move a HDD with a Windows NT to a new computer (or replace motherboard) without problems if the new hardware is identical to the old one. If this is not the case, then the easiest solution for home users is to make a [Inplace Upgrade of Windows NT](/article/winnt-repair-install.html) on top of the existing install on the new computer.  
   Another way is to uninstall all motherboard specific drivers BEFORE moving the HDD to different hardware (Can usually be done through Add/Remove software in the Control Panel). 
  - IDE Drivers
  - AGP/PCI Drivers
  - USB Drivers
   
   Remember to check for [Ghost devices](/article/winnt-ghost-devices.html) left from the old hardware. AFTER changing the motherboard, then one might have to boot into the [Recovery Console](/article/winnt-recovery-console.html) using a Windows XP Install CD, and perform the command **bootcfg /rebuild**.  
    
   More Info [MS KB249694](http://support.microsoft.com/kb/249694 "How to Move a Windows 2000 Installation to Different Hardware [Q249694]")  
   More Info [MS KB268066](http://support.microsoft.com/kb/268066 "Startup Problems When Transferring System Hard Disk to a Backup Computer [Q268066]")  
   More Info [MS KB314082](http://support.microsoft.com/kb/314082 "You Receive a Stop 0x0000007B Error After You Move the Windows XP System Disk to Another Computer [Q314082]")  
   More Info [MS KB316401](http://support.microsoft.com/kb/316401 ""STOP 0x0000007B" Error Message When You Restart Your Windows XP-Based Computer [Q316401]")
- **When having updated drivers for the HDD-Controller:**  
   The only option is to rollback to the previous drivers. This can be done by booting into the [Recovery Console](/article/winnt-recovery-console.html) and manually copy the old drivers into %Windir%\\System32\\Drivers and overwrite the new ones. Then boot using [Last Known Good Configuration (LKGC)](/article/winnt-last-known-good-configuration.html), and it should be in the before the drivers were loaded. If LKGC doesn't work try to [Use Recovery Console to recover from a faulty registry.](/article/winnt-recovery-console-registry-restore.html).  
    
   If using WinXP and one have got the computer up and running, then one can use System-Restore to go forward to the newest version of the registry just before installing the drivers.  
    
   Generally it is a good idea to make a backup of the System-Registry-File %Windir%\\System32\\Config\\System and the existing drivers, before changing the drivers for the HDD-Controller where the boot-device is attached. (The backup allows one to easily go back in case something fails)  
    
   More Info [MS KB307545](http://support.microsoft.com/kb/307545 "How to Recover from a Corrupted Registry that Prevents Windows XP from Starting [Q307545]")
- **When having updated firmware HDD-Controller without updating drivers first:**  
   If updating firmware then usually new drivers are supplied too. It is good idea to apply the drivers first and boot on a floppy to change the firmware. If one have changed the order and changed the firmware first, then one can try to go back to the old version of the firmware to recover.  
    
   This is also the case when changing from a Promise Fasttrak66 to a Promise Fasttrak100, one have to force install the drivers before making the swap of controllers. This way the Windows NT install on the RAID-Array will recognize the new hardware-id of the new controller.
- **When having installed a Microsoft Windows Service Pack/Hotfix/Patch:**  
   There have been several occasions where the ATAPI.SYS has been updated with a Service Pack and have caused this BSOD. To restore operation exchange the updated ATAPI.SYS with the old ATAPI.SYS (From Install-Cd or Uninstall directory made during Service Pack install) by booting from [Recovery Console](/article/winnt-recovery-console.html). The Recovery console can also be used to uninstall the hotfix by using the BATCH command (Where XXXXXX is the hotfix id):
   > BATCH %systemroot%\\$NTUninstallKBXXXXXX$\\spuninst.txt
  
   More Info [MS KB161960](http://support.microsoft.com/kb/161960 "STOP 0x0000007B On Windows NT 4.0 After SP2 Applied [Q161960]")  
   More Info [MS KB825062](http://support.microsoft.com/kb/825062 "Service Pack 4 Permits You to Remove the Service Pack by Using the Recovery Console [Q825062]")  
   More Info [MS KB875350](http://support.microsoft.com/kb/875350 "How to remove Windows XP Service Pack 2 from your computer [Q875350]")
- **When a hardware error has occurred**  
   This is usually caused by a defective HDD, Cabel, Controller or Motherboard. Replace the defective unit with an identical working one.
- **When changing the SATA mode of the boot drive**  
   Motherboards with onboard SATA HDD controllers, can support different modes for the SATA controller: 
  - Advanced Host Controller Interface (AHCI) is the most optimal, which supports the new SATA features like Native Command Queuing (NCQ) and hot swap.
  - Parallel Advanced Technology Attachment (PATA) is an emulated mode, which enables SATA drives to appear like standard IDE ATA drives.
   
   Windows 2000/XP doesn't support AHCI out of the box, and requires 3rd party drivers to install if the bootdrive is attached such a controller. It is possible to install using emulated PATA and then install the proper drivers, then change the controller to AHCI in the motherboard BIOS.  
    
   Windows Vista is special as it supports both PATA and AHCI, but if no devices attached to a controller then it automatically disables the drivers. This means that if having installed in emulated PATA and then changing to AHCI then it will fail to boot. One manually have to activate the driver before changing the SATA mode:
  > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Msahci\]  
  >  Start = 0  
  >   
  >  More Info [MS KB922976](http://support.microsoft.com/kb/922976 "Error message when you start a Windows Vista-based computer after you change the SATA mode of the boot drive: "STOP 0x0000007B INACCESSABLE_BOOT_DEVICE"")
 
 More Info [MS KB122926](http://support.microsoft.com/kb/q122926 "Troubleshooting Stop 0x0000007B or "0x4,0,0,0" Error [Q122926]")  
 More Info [MS KB324103](http://support.microsoft.com/kb/324103 "HOW TO: Troubleshoot "Stop 0x0000007B" Errors in Windows XP [Q324103]")  
 More Info [MS KB822052](http://support.microsoft.com/kb/822052 "How to troubleshoot "Stop 0x0000007B" error messages in Windows 2000 [Q822052]") (Replaces MS KB271965, KB824207)  