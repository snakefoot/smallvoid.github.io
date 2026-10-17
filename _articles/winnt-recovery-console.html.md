---
title: 'Using Recovery Console in Windows 2000 / XP'
date: '2001-06-05T00:34:29+02:00'
permalink: /article/winnt-recovery-console.html
author: Snakefoot
excerpt: 'Recovery Console can be useful when performing system recovery.'
type: post
id: 250
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-xp_troubleshoot
tags:
    - recovery-console
    - system-recovery
---
The Recovery Console is a command prompt environment that is useful for emergency repair of the normal Windows installation (Like creating the Emergency Recover Disks). One can access the recovery console by booting from a Windows 2000/XP install CD-ROM:

1. Insert the Windows install CD-ROM, and boot the computer.
2. When the text-based part of Setup begins, follow the prompts. Select the repair or recover option by pressing **R**.
3. Select the Windows installlation you want to repair and enter your Administrator password.
 
 Note the password for the builtin administrator account on Windows XP is usually blank, so just press enter when it requests for a password.  
  
 Note one still need to have a floppy disk with 3rd party drivers for SCSI/SATA and such, when booting with the Recovery Console. Unless [Installing Recovery Console with 3rd party controller drivers](/article/recovery-console-drivers.html)  
  
 Note the Recovery Console can also be used to repair old Windows NT4 installations.  
  
 More info <a href="https://www.bing.com/search?q=KB+229716+Q229716" rel="nofollow" title="Description of the Windows 2000 Recovery Console (MS KB229716) [Q229716]">MS KB229716</a>  
 More info <a href="https://www.bing.com/search?q=KB+326215+Q326215" rel="nofollow" title="HOW TO: Use the Recovery Console on a Windows Server 2003-Based Computer That Does Not Start [Q326215]">MS KB326215</a>  
 More info <a href="https://www.bing.com/search?q=KB+313670+Q313670" rel="nofollow" title="HOW TO: Replace a Driver by Using Recovery Console in Windows 2000 [Q313670]">MS KB313670</a>  
 More info <a href="https://www.bing.com/search?q=KB+301645+Q301645" rel="nofollow" title="HOW TO: Use Recovery Console on a Computer That Does Not Start in Windows 2000 [Q301645]">MS KB301645</a>  
 More info <a href="https://www.bing.com/search?q=KB+314058+Q314058" rel="nofollow" title="Description of the Windows XP Recovery Console for advanced users">MS KB314058</a>  
##### Useful commands in the Recovery Console

- FIXBOOT - Restores the boot sector in case another OS (Ex. Win98) has overwritten it, and sets the boot partition as active partition.
- FIXMBR - Restores the master boot record(MBR) in case a virus or similar has corrupted it
- DISKPART - HDD Partition Utility (Similar to FDISK in DOS)
- CHKDSK - Scandisk utility (The "/r" -option is good when getting "Delayed Write Failed" errors. More Info <a href="https://www.bing.com/search?q=KB+330174+Q330174" rel="nofollow" title="'Delayed Write Failed' Error Message When You Manage Files in Windows XP [Q330174]">MS KB330174</a>)
- LISTSVC - Shows services installed, when launched in the WINNT\\SYSTEM32 folder.
- DISABLE &lt;service name&gt; - Will disable the service specified when launched in the WINNT\\SYSTEM32 folder (Which might keep your system from booting)
- ENABLE &lt;service name&gt; - Will enable the service specified when launched in the WINNT\\SYSTEM32 folder (Which might enable your system to boot)
- EXPAND - Makes it possible to restore compressed system files from the install cd. (Ex. ATAPI.SYS)
- BATCH - Makes it possible to execute batch files. (Ex. to uninstall hotfix/patches from Microsoft). More Info <a href="https://www.bing.com/search?q=KB+825062+Q825062" rel="nofollow" title="Service Pack 4 Permits You to Remove the Service Pack by Using the Recovery Console [Q825062]">MS KB825062</a>
- BOOTCFG - Makes it easier to configure/rebuild the boot manager [boot.ini](/article/winnt-boot-ini.html) (WinXP+ only). More info <a href="https://www.bing.com/search?q=KB+291980+Q291980" rel="nofollow" title="A Discussion About the Bootcfg Command and Its Uses [Q291980]">MS KB291980</a> More info <a href="https://www.bing.com/search?q=KB+317521+Q317521" rel="nofollow" title="Description of the BOOTCFG Command and Its Uses [Q317521]">MS KB317521</a>
- [Using Recovery Console to restore registry files](/article/winnt-recovery-console-registry-restore.html)
 
 More info <a href="https://www.bing.com/search?q=KB+235364+Q235364" rel="nofollow" title="Description of the SET Command in Recovery Console (MS KB235364) [Q235364]">MS KB235364</a>  
##### Configure Recovery Console Security

 Note one can lessen the security for the recovery console to have easier access. Run "secpol.msc" and go here "Local Policies" -&gt; "Security Options" - "Recovery Console: Allow Automatic Administrative Logon" : Then you don't need to remember your admin password (People still need to get physical access to the machine)
- "Recovery Console: Allow floppy copy and access to all drives and all folders" : To give you access to the whole machine
 
 More info <a href="https://www.bing.com/search?q=KB+310497+Q310497" rel="nofollow" title="HOW TO: Add More Power to Recovery Console By Using Group Policy in Windows XP Professional [Q310497]">MS KB310497</a>  
 More info <a href="https://www.bing.com/search?q=KB+312149+Q312149" rel="nofollow" title="HOW TO: Enable Administrator to Log On Automatically in Recovery Console [Q312149]">MS KB312149</a>  
<a name="INSTALL"></a>
##### Installing Recovery Console

 Instead of having to find the Windows install CD every time the Recovery Console is needed, then one can install the Recovery Console on the computer. This is also useful if the computer cannot boot from a CD-ROM.  
  
 Inside Windows run the following command (X: is your CD-Drive containing the Windows CD-ROM)
 > X:\\i386\\winnt32.exe /cmdcons

 Note when having installed the Recovery Console on the computer, then it becomes part of the standard boot menu. It is possible to [install extra drivers to the Recovery Console](/article/recovery-console-drivers.html), so one doesn't need extra floppies to load disk controller drivers (Also useful if there is no floppy drive in the computer).  
  
 Note that if the system drive is mirrored, then you need to break the mirror before installing Recovery Console and then create the mirror again with Disk Administrator.  
  
 More info <a href="https://www.bing.com/search?q=KB+307654+Q307654" rel="nofollow" title="HOW TO: Install and Use the Recovery Console in Windows XP (MS KB307654) [Q307654]">MS KB307654</a>  
 More info <a href="https://www.bing.com/search?q=KB+318752+Q318752" rel="nofollow" title="HOW TO: Install and Use the Recovery Console in Windows 2000 [Q318752]">MS KB318752</a>  