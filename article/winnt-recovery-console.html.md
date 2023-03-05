---
title: 'Using Recovery Console in Windows 2000 / XP'
date: '2001-06-05T00:34:29+02:00'
status: publish
permalink: /article/winnt-recovery-console.html
author: Snakefoot
excerpt: 'Recovery Console can be useful when performing system recovery.'
type: post
id: 250
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - recovery-console
    - system-recovery
post_format: []
tags:
    - 'recovery-console,system-recovery'
---
The Recovery Console is a command prompt environment that is useful for emergency repair of the normal Windows installation (Like creating the Emergency Recover Disks). One can access the recovery console by booting from a Windows 2000/XP install CD-ROM:

1. Insert the Windows install CD-ROM, and boot the computer.
2. When the text-based part of Setup begins, follow the prompts. Select the repair or recover option by pressing **R**.
3. Select the Windows installlation you want to repair and enter your Administrator password.
 
 Note the password for the builtin administrator account on Windows XP is usually blank, so just press enter when it requests for a password.  
  
 Note one still need to have a floppy disk with 3rd party drivers for SCSI/SATA and such, when booting with the Recovery Console. Unless [Installing Recovery Console with 3rd party controller drivers](/article/recovery-console-drivers.html)  
  
 Note the Recovery Console can also be used to repair old Windows NT4 installations.  
  
 More info [MS KB229716](http://support.microsoft.com/kb/229716 "Description of the Windows 2000 Recovery Console (MS KB229716) [Q229716]")  
 More info [MS KB326215](http://support.microsoft.com/kb/326215 "HOW TO: Use the Recovery Console on a Windows Server 2003-Based Computer That Does Not Start [Q326215]")  
 More info [MS KB313670](http://support.microsoft.com/kb/313670 "HOW TO: Replace a Driver by Using Recovery Console in Windows 2000 [Q313670]")  
 More info [MS KB301645](http://support.microsoft.com/kb/301645 "HOW TO: Use Recovery Console on a Computer That Does Not Start in Windows 2000 [Q301645]")  
 More info [MS KB314058](http://support.microsoft.com/kb/314058 "Description of the Windows XP Recovery Console for advanced users")  
##### Useful commands in the Recovery Console

- FIXBOOT - Restores the boot sector in case another OS (Ex. Win98) has overwritten it, and sets the boot partition as active partition.
- FIXMBR - Restores the master boot record(MBR) in case a virus or similar has corrupted it
- DISKPART - HDD Partition Utility (Similar to FDISK in DOS)
- CHKDSK - Scandisk utility (The "/r" -option is good when getting "Delayed Write Failed" errors. More Info [MS KB330174](http://support.microsoft.com/kb/330174 ""Delayed Write Failed" Error Message When You Manage Files in Windows XP [Q330174]"))
- LISTSVC - Shows services installed, when launched in the WINNT\\SYSTEM32 folder.
- DISABLE &lt;service name&gt; - Will disable the service specified when launched in the WINNT\\SYSTEM32 folder (Which might keep your system from booting)
- ENABLE &lt;service name&gt; - Will enable the service specified when launched in the WINNT\\SYSTEM32 folder (Which might enable your system to boot)
- EXPAND - Makes it possible to restore compressed system files from the install cd. (Ex. ATAPI.SYS)
- BATCH - Makes it possible to execute batch files. (Ex. to uninstall hotfix/patches from Microsoft). More Info [MS KB825062](http://support.microsoft.com/kb/825062 "Service Pack 4 Permits You to Remove the Service Pack by Using the Recovery Console [Q825062]")
- BOOTCFG - Makes it easier to configure/rebuild the boot manager [boot.ini](/article/winnt-boot-ini.html) (WinXP+ only). More info [MS KB291980](http://support.microsoft.com/kb/291980 "A Discussion About the Bootcfg Command and Its Uses [Q291980]") More info [MS KB317521](http://support.microsoft.com/kb/317521 "Description of the BOOTCFG Command and Its Uses [Q317521]")
- [Using Recovery Console to restore registry files](/article/winnt-recovery-console-registry-restore.html)
 
 More info [MS KB235364](http://support.microsoft.com/kb/235364 "Description of the SET Command in Recovery Console (MS KB235364) [Q235364]")  
##### Configure Recovery Console Security

 Note one can lessen the security for the recovery console to have easier access. Run "secpol.msc" and go here "Local Policies" -&gt; "Security Options" - "Recovery Console: Allow Automatic Administrative Logon" : Then you don't need to remember your admin password (People still need to get physical access to the machine)
- "Recovery Console: Allow floppy copy and access to all drives and all folders" : To give you access to the whole machine
 
 More info [MS KB310497](http://support.microsoft.com/kb/310497 "HOW TO: Add More Power to Recovery Console By Using Group Policy in Windows XP Professional [Q310497]")  
 More info [MS KB312149](http://support.microsoft.com/kb/312149 "HOW TO: Enable Administrator to Log On Automatically in Recovery Console [Q312149]")  
<a name="INSTALL"></a>
##### Installing Recovery Console

 Instead of having to find the Windows install CD every time the Recovery Console is needed, then one can install the Recovery Console on the computer. This is also useful if the computer cannot boot from a CD-ROM.  
  
 Inside Windows run the following command (X: is your CD-Drive containing the Windows CD-ROM) > X:\\i386\\winnt32.exe /cmdcons

 Note when having installed the Recovery Console on the computer, then it becomes part of the standard boot menu. It is possible to [install extra drivers to the Recovery Console](/article/recovery-console-drivers.html), so one doesn't need extra floppies to load disk controller drivers (Also useful if there is no floppy drive in the computer).  
  
 Note that if the system drive is mirrored, then you need to break the mirror before installing Recovery Console and then create the mirror again with Disk Administrator.  
  
 More info [MS KB307654](http://support.microsoft.com/kb/307654 "HOW TO: Install and Use the Recovery Console in Windows XP (MS KB307654) [Q307654]")  
 More info [MS KB318752](http://support.microsoft.com/kb/318752 "HOW TO: Install and Use the Recovery Console in Windows 2000 [Q318752]")  