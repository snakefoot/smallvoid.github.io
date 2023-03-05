---
title: 'Enable Driver Verifier to troubleshoot faulty driver'
date: '2005-09-25T01:36:49+02:00'
status: publish
permalink: /article/winnt-driver-verifier.html
author: Snakefoot
excerpt: 'Driver Verifier can be used to stress device drivers and can detect if the drivers performs illegal operations.'
type: post
id: 471
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - blue-screen-of-death
    - driver-verifier
post_format: []
tags:
    - 'driver-verifier,blue-screen-of-death'
---
The Driver Verifier Manager is a tool created by Microsoft to diagnostic installed drivers, and is used by Windows Hardware Quality Labs (WHQL). The tool tests how drivers handles certain "extreme" situations with limited resources (Ex. low memory) or failing function calls.  
  
 The tool is mainly for driver developers to help them test their own driver before it is actually released. It is possible for the average user to use this tool, but one should make sure to have created a backup of important documents first before doing this. This precaution is necessary because ex. stress testing the disk-drivers can lead to data-loss.

- Before starting make sure to make a backup of the system registry, so one can rollback the system if the driver verifier makes a driver fails so the system is unable to boot properly: 
  - Win2k+ - Emergency Recovery Disk
  - WinXP+ - Automatic System Recovery
  - [Ntbackup](/article/winnt-ntbackup.html) to backup System State and use [Recovery Console](/article/winnt-recovery-console-registry-restore.html) to restore the registry
  - [Regback](/article/winnt-registry-backup.html) to backup registry files and use [Recovery Console](/article/winnt-recovery-console-registry-restore.html) to restore the registry
- Start the Driver Verifier Manager with this command:
  > Verifier.exe
- Configure what drivers to verify (Don't verify all drivers as it will become painfully slow): 
  - Win2k: Select **Settings**-tab to configure what drivers to verify
  - WinXP: Select **Create standard settings** to choose what type of drivers to verify
- Reboot and if any problems a Blue Screen Of Death (BSOD) will appear showing the problem driver 
  - Don't perform a logon within the first 30 minutes (Disable [Automatic Login](/article/winnt-automatic-logon.html)), or else one will loose the ability to rollback easily using [Last Known Good Configuration](/article/winnt-last-known-good-configuration.html)
- Turnoff the Driver Verifier with this command:
  > Verifier.exe /reset
 
 More Info [MS KB244617](http://support.microsoft.com/kb/244617 "How to Use Driver Verifier to Troubleshoot Windows Drivers [Q244617]")  
 More Info [MS KB251233](http://support.microsoft.com/kb/251233 "Things to consider before you enable Driver Verifier Manager on production servers [Q251233]")  
 More Info [MS KB325672](http://support.microsoft.com/kb/325672 "Fatal System Error: 0x000000C4 If Deadlock Detection in Driver Verifier Is Turned on and Norton Antivirus Is Installed [Q325672]") (Careful with Norton Antivirus)  
 More Info [Windows Hardware and Driver Central: Driver Verifier](http://www.microsoft.com/whdc/DevTools/tools/DrvVerifier.mspx)  
  
 Related [Analyze blue screen of death crash dumps to find faulty driver](/article/winnt-windbg.html)  
  
 Credits [OneComputerGuy.com](http://onecomputerguy.com/)