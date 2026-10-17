---
title: 'Recover Windows installation by repair or reinstall'
date: '2004-06-10T21:38:33+02:00'
permalink: /article/winnt-repair-install.html
author: Snakefoot
excerpt: 'Different solutions for recovering a broken Windows installation.'
type: post
id: 395
categories:
    - windows-2000_troubleshoot
    - windows-xp_troubleshoot
tags:
    - automatic-system-recovery
    - last-known-good-configuration
    - recovery-console
    - system-file-checker
    - system-recovery
    - system-state
---
Microsoft Windows 2000/XP are able to run for a long time without starting to get serious quirks from changing hardware / software / user-settings (Compared to older versions of Windows).  
  
 But it is still happens from time to time that Windows stops working as it should, and one can try to repair or just throw in the towel and erase everything and start over. Luckily lots of different options are available for doing system recovery, so even if have tried the following simple methods for recovering, then everything isn't lost as more options are available (see further below):

- Checked for [Hardware conflicts](/article/repair-hardware-conflict.html)
- **Add/Remove Programs** to uninstall whatever application that have caused the problem (Also works in safemode)
- **System File Checker** ([SFC](/article/winnt-sfc.html)) to repair any corrupted system files.
- [Debugging Tools](/article/winnt-windbg.html) to diagnose the memory dumps created by Blue Screen of Death (BSOD).
- **Driver Rollback** to change back to an older version of the driver or just uninstall the device in case it is causing the problem (Also works in safemode)
- **System Restore** (WinXP only) to restore: (Also works in safemode) 
  - Files with extensions listed in the &lt;include&gt; portion of [Monitored File Extensions list](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/sr/sr/monitored_file_extensions.asp)
  - The COM+ class registration database
  - The registry
  - IIS Metabase
  - Local User Profiles (Not roaming)
  - WFP.dll cache
  - WMI Database
- **System State** (Win2k+) (Requires that a backup manually have been made with Ntbackup) to restore: (Also works in safemode) 
  - The system boot files (Doesn't include 3rd party drivers)
  - The COM+ class registration database
  - The registry
  - The IIS metabase.
  - Active Directory (NTDS) (Domain Controller only)
  - The system volume (SYSVOL) (Domain Controller only)
 
 If the above repair-options is not available because Windows refuses to boot then try these:
- [Last Known Good Configuration](/article/winnt-last-known-good-configuration.html) if a change made before restarting caused Windows not to boot
- **Emergency Recovery Console**, which can boot the machine from a CD-ROM with repair/backup utilities: 
  - [Recovery Console](/article/winnt-recovery-console.html) (Chkdsk, Fixboot, Bootcfg, [Restore Registry Files](/article/winnt-recovery-console-registry-restore.html))
  - [Bart's PE or Knoppix Linux Live](/article/winnt-preinstalled-environment.html)
  - **Emergency Repair Process**: (WinNT4/Win2k only) 
      - Boot from the Install-CD
      - Press "R" to perform a repair
      - Press "R" to use "Emergency Repair process"
      - Press "M" to do Manual Repair (Don't press "F" for Fast Repair)
      - Gives the following options: 
            - Inspect Startup Environment (Similar to Recovery Console command Bootcfg)
            - Verify Windows System Files (Similar to [SFC](/article/winnt-sfc.html))
            - Inspect Boot Sector (Similar to Recovery Console command chkdsk and fixboot)
            - More Info <a href="https://www.bing.com/search?q=KB+238359+Q238359" rel="nofollow" title="Differences Between Manual and Fast Repair in Windows [Q238359]">MS KB238359</a>
             
             \*Important\* if it is a Domain Controller then these options will overwrite \\WinNT\\NTDS\\ntds.dit. More Info <a href="https://www.bing.com/search?q=KB+238359+Q238359" rel="nofollow" title="HOW TO: Use the Backup Program to Back Up and Restore the System State in Windows 2000 [Q238359]">MS KB238359</a>
- **Automatic System Recovery**: (WinXP only) 
  - It requires that one have created a ASR Floppy Disk and BKF-file(image) using NTBackup
  - Boot from the Install-CD
  - Press "F2" when it is written in the bottom of the screen (Short Time)
  - Insert the ASR Floppy Disk and press Enter (Quit now if you don't want your C-drive formatted)
  - After the text-mode install, then it will launch NTBackup and restore from the BKF-file (image)
- **Reinstall on top of existing installation** (Inplace upgrade):  
   If able to perform Windows Login: 
  - Disconnect from the Internet (Pull the cable) to avoid being attacked during reinstall
  - Insert the Install-CD (It should [automatically](/article/winnt-autorun.html) show a welcome screen to Windows Setup)
  - Follow the instructions to do an "Upgrade"
  - It should be the same (but easier) to execute this command (X: is CD-Driveletter):
    > X:\\i386\\Winnt32 /unattend
   
   If unable to get inside Windows: 
  - Disconnect from the Internet (Pull the cable) to avoid being attacked during reinstall
  - Boot from the Install-CD
  - Press Enter to "Setup Windows Now" at the "Welcome to Setup"-screen (Don't press "R")
  - Press F8 to agree to the license agreement
  - Make sure your current installation of Windows is selected and press "R" to start the repair 
      - If it is not possible to select the current installation of Windows, then an inplace-upgrade isn't possible
   
   \*Important\* when doing an inplace upgrade: 
  - Before the inplace upgrade then make sure to delete the following file (Only OEM install of WinXP):
    > %windir%\\system32\\undo\_guimode.txt
      
       More Info <a href="https://www.bing.com/search?q=KB+312369+Q312369" rel="nofollow" title="You May Lose Data or Program Settings After Reinstalling, Repairing, or Upgrading Windows XP [Q312369]">MS KB312369</a>
  - After the inplace upgrade then make sure to reinstall all updates, and reapply all Windows registry tweaks.  
        
       More Info <a href="https://www.bing.com/search?q=KB+306952+Q306952" rel="nofollow" title="What an in-place Windows 2000 upgrade changes and what it does not change [Q306952]">MS KB306952</a>
   
   More Info <a href="https://www.bing.com/search?q=KB+292175+Q292175" rel="nofollow" title="How to Perform an In-Place Upgrade of Windows 2000 [Q292175]">MS KB292175</a> (Previous MS KB287043)  
   More Info <a href="https://www.bing.com/search?q=KB+315341+Q315341" rel="nofollow" title="How to perform an in-place upgrade (reinstallation) of Windows XP [Q315341]">MS KB315341</a>  
   More Info <a href="https://www.bing.com/search?q=KB+316941+Q316941" rel="nofollow" title="HOW TO: Install Windows XP [Q316941]">MS KB316941</a>
 
 More Info <a href="https://www.bing.com/search?q=KB+315396+Q315396" rel="nofollow" title="HOW TO: Troubleshoot Startup Problems in Windows 2000 [Q315396]">MS KB315396</a>  
 More Info <a href="https://www.bing.com/search?q=KB+316434+Q316434" rel="nofollow" title="How to perform advanced clean-boot troubleshooting in Windows XP [Q316434]">MS KB316434</a>  
 More Info <a href="https://www.bing.com/search?q=KB+325375+Q325375" rel="nofollow" title="HOW TO: Troubleshoot Startup Problems in Windows Server 2003 [Q325375]">MS KB325375</a>  
 More Info [WinXP Reskit: Troubleshooting Startup](http://www.microsoft.com/mspress/books/sampchap/6795.asp "Microsoft® Windows® XP Professional Resource Kit, Second Edition")  