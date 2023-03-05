---
title: 'Reset Administrator password to recover access'
date: '2000-01-01T01:26:47+01:00'
status: publish
permalink: /article/winnt-reset-password.html
author: Snakefoot
excerpt: 'Deleting the password storage files to reset the Administrator password to recover system access.'
type: post
id: 255
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - administrator
    - password
    - password-recovery
    - sam-database
    - system-recovery
    - windows-login
post_format: []
tags:
    - 'administrator,password-recovery,password,sam-database,windows-login,system-recovery'
---
Different ways to recover a forgotten / lost password:

- If there is another Administrator account then use that account to login and change the password for the problem account.  
    
   Note in WinXP Home the builtin Administrator account has by default no password, but is only accessible through safemode, useful if forgotten the password for another account.  
    
   Note if the user has encrypted files or e-mail messages, or have stored passwords for websites or network resources, then these will be losts if using an Administrator account to reset the password.
- If using Windows XP and have been foreseeing to create password recovery disks, then they can be used: 
  - [Creating password reset disk when in a domain](http://support.microsoft.com/kb/306214 "How to create and use a password reset disk for a computer in a domain in Windows XP [Q306214]")
  - [Creating password reset disk when NOT in a domain](http://support.microsoft.com/kb/305478 "How to create and use a password reset disk for a computer that is not a domain member in Windows XP [Q305478]")
   
   Note Vista also include the option to [Create a password reset disk](http://windowshelp.microsoft.com/Windows/en-US/Help/5bf12a40-12b5-4ca8-87c3-7741adbd15841033.mspx)
- Use a 3rd party [Password Remover](/article/winnt-password-recovery.html), which is also able to edit the SAM (Security Accounts Manager) files and reset the password without damaging the other accounts.  
    
   Note this will not work for a domain Administrator account, but it can be done: 
  1. Use the Password Remover to reset the password for the local Administrator.
  2. Boot into safemode which disables the Active Directory(AD).
  3. Login with the local Administrator and then follow the steps described below to change the login screensaver and recovery of password for a domain controller.
- Change the login screensaver to gain access to user management: 
  1. Replace the %systemroot%\\System32\\Logon.scr with Explorer.exe or Cmd.exe 
      - If having access to the registry one can instead change the screensaver with this registry value:
            > \[HKEY\_USERS\\ .Default\\ Control Panel\\ Desktop\]  
            >  SCRNSAVE.EXE = "cmd.exe"  
            >  ScreenSaveTimeOut = 15 (Default = 900 secs)  
            >  ScreenSaveActive = 1 (Default = 0)  
            >   
            >  More Info [MS KB185348](http://support.microsoft.com/kb/185348 "HOW TO: Change the Logon Screen Saver in Windows [Q185348]")
  2. Boot WinNT/2k/Xp and wait for the login screensaver (Not touching keyboard / mouse).
  3. My Computer or Command Prompt will come up after 15 minutes.
  4. Change the password: 
      - If using WinNT run %systemroot%\\MUSRMGR ( If a Domain Controller %systemroot%\\USRMGR )
      - If using Win2k run %systemroot%\\Compmgmt.msc ( If a Domain Controller %systemroot%\\DSA.MSC )
      - If using Command Prompt one can also use this command:
        > NET USER \[username\] \[newpassword\]
  5. Revert the screensaver changes so My Computer or Command Prompt doesn't popup at login.
- Replace [Sticky keys](/article/winnt-sticky-keys.html) executable and use sticky keys to open Command Prompt or Windows Explorer (Windows 2000, XP, Vista) 
  1. Replace %systemroot%\\System32\\sethc.exe with Explorer.exe or Cmd.exe
  2. Boot Windows and wait for the login screen to show, then press the Shift-key 5 times to activate sticky keys.
  3. Now change the password like if having replaced the login screensaver (See above).
- Delete the 3 files SAM , SAM.SAV and SAM.LOG in the directory WINNT\\System32\\Config. This will erase all accounts with rights and passwords, but the builtin Administrator account will survive with no password.  
    
   Note even if deleting the SAM-files the users profile directories with settings still exists. One can create a new user and [change the default profile directory](/article/winnt-move-userprofile.html) to point to an old profile directory and use the settings stored there.
 
 Different ways to get access to replace or delete files:
- If WinNT is installed on FAT16 or 32 partition then use a standard [bootdisk](/article/dos-bootdisk.html) for Win9x to access to the partition.
- Use [Knoppix Linux CD](/article/winnt-preinstalled-environment.html) to boot Linux with NTFS access and registry editor.
- Use [Bart's PE CD](/article/winnt-preinstalled-environment.html) to boot Windows XP/2003 with NTFS access and registry editor.
- Install a parallel WinNT/2k/Xp and boot the parallel WinNT/2k/Xp and you will have access to the original installation files along with the [offline registry](/article/winnt-offline-registry-edit.html).
- If WinXP one can use the Win2k Install CD to login to the [Recovery Console](/article/winnt-recovery-console.html) without needing a password.
- Take the HDD and put it into another machine running the same or higher version of Windows and access the files and the [offline registry](/article/winnt-offline-registry-edit.html) using that machine.
 
 More Info [MS KB321305](http://support.microsoft.com/kb/321305 "How to Log On to Windows XP If You Forget Your Password or Your Password Expires [Q321305]")  