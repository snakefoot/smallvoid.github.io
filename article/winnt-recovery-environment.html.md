---
title: 'Windows Recovery Environment'
date: '2007-10-30T01:03:49+01:00'
status: publish
permalink: /article/winnt-recovery-environment.html
author: Snakefoot
excerpt: 'Windows Vista includes a Windows Preinstallation Environment, which allows easier and more advanced system recovery.'
type: post
id: 753
category:
    - Troubleshoot
tag:
    - preinstallation-environment
    - system-recovery
    - windows-recovery-environment
post_format: []
tags:
    - 'windows-recovery-environment,system-recovery,preinstallation-environment'
---
Windows Vista introduces the Windows Recovery Environment (Windows RE or WinRE), which completely replaces the [Recovery Console](/article/winnt-recovery-console.html). WinRE is actually a [Windows Preinstallation Environment](/article/winnt-preinstalled-environment.html) (Windows PE), which enables much more advanced tools for system diagnosis and recovery.  
  
 To access the WinRE using the Vista install disk:

1. Boot from the Vista install disk
2. Choose your language settings and click "Next"
3. On the bottom of the screen click the link "Repair Your Computer"
4. Select the Vista installation to repair and click "Next" and it will launch WinRE 
  - The "Load Drivers" button will open a mini Windows Explorer, which can be used to search for drivers in case they are needed to access disk drives or other components. This mini Explorer is also very handy to perform file copy/move operations and change file-attributes.
 
 The following options are available in WinRE: - **Startup Repair** - It will repair the boot manager files and restore critical files required for booting Windows Vista.  
    
   After attempting to repair the system it will display a Startup Repair diagnosis and repair log with the different Test Performed and the probably root cause.
- **System Restore** - Windows Vista automatically performs daily backups of system critical files and also before installation of drivers and applications. These backups are called system restore points, and this option makes it possible to restore the system state before the moment it started to fail.
- **Windows Complete PC Restore** - If having performed a backup of the entire system, then this option can be used to restore that backup.
- **Windows Memory Diagnostic Tool** - Memory modules can be sensitive to things like working with other memory modules, system-bus frequencies, motherboard models, overclocking etc. When the memory modules fails to work properly then the computer will become unstable especially when under load. More Info [Windows Help](http://windowshelp.microsoft.com/Windows/en-US/Help/4edd5f80-def2-4d32-965c-116d49fb98721033.mspx "How do I know if my computer has a memory problem?")
  - If wanting to access the Memory Diagnostic Tool without installing Vista first, then boot from the Vista Install Disk, and when it says "Press any key to boot from CD or DVD..." hold down the Space-bar or press it multiple times. This should bring up the Windows boot manager, which has "Windows Memory Diagnostic" as an option.
- **Command Prompt** - Pretty much the same as the Recovery Console. Among other things it gives access to the boot manager configuration. More Info [MS KB927392](http://support.microsoft.com/kb/927392 "How to use the Bootrec.exe tool in the Windows Recovery Environment to troubleshoot and repair startup issues in Windows Vista"): 
  - **Bootrec.exe /FixMbr** - Rewrites the Master Boot Record (MBR) for the boot partition.
  - **Bootrec.exe /FixBoot** - Rewrites the boot sector for the boot partition.
  - **Bootrec.exe /ScanOs** - Scans all disk for bootable partitions and displays the entries not in the BCD store.
  - **Bootrec.exe /RebuildBcd** - Scans all disk for bootable partitions and allows one to decide what entries to rebuild the BCD store from (Similar to Bootcfg /rebuild in XP).
  - [BCDEdit.exe](/article/winnt-bootmgr-config.html) - Can backup / restore the Boot Configuration Data (BCD) store. Can change the boot manager options for a certain entry in the BCD.
   
   Note the old Recovery Console commands to work with services and drivers (LISTSVC, ENABLE, DISABLE) are no longer available, but instead one can use [regedit to edit registry hive offline](/article/winnt-offline-registry-edit.html) and change the [startup setting for the service or driver](/article/winnt-services-regedit.html).
 
 Note if not having the Vista install disc then the system builder might have created a hidden partition for the Windows Recovery Environment (WinRE). If this is the case then WinRE should be available when pressing the F8 key during startup (Like if booting into safemode). More Info [How to install WinRE locally](http://www.svrops.com/svrops/articles/winvistare.htm)