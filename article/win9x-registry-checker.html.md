---
title: 'Command line Parameters for SCANREG'
date: '2001-01-03T19:58:23+01:00'
status: publish
permalink: /article/win9x-registry-checker.html
author: Snakefoot
excerpt: 'Scanreg command line switches for checking the Windows registry.'
type: post
id: 109
category:
    - Tips
    - Tips
tag:
    - command-line-switches
    - registry-checker
    - scanreg
post_format: []
tags:
    - 'scanreg,registry-checker,command-line-switches'
---
The Registry Checker Tool arrived with Win98/Me, and makes it easy to backup or restore the registry. The DOS version of the Registry Checker (Scanreg.exe) has the following command line switches:

> Scanreg.exe \[/backup\] \[/restore\] \["/comment=&lt;text&gt;"\] \[/fix\] \[/opt\]
> 
> - /backup - backups the registry (System.dat and User.dat), System.ini and Win.ini
> - /restore - brings up a list of backed up registries and lets you select which you want to restore (Only the 5 earliest backups are displayed)
> - /comment - lets you add a comment when backing up your registry
> - /fix - fixes any errors and removes unused spaces by rebuilding the registry
> - /opt - optimizes the registry by removing any gaps larger than 500 KBytes
> - /autoscan - Scans the registry and creates a backup without prompting user
> - /scanonly - Scans the registry for errors without making any changes

 The Windows version of the Registry Checker (Scanregw.exe) has the same switches, but it cannot optimize or restore the registry. By default when Windows starts the Registry Checker is launched like this:
 > Scanregw.exe /autorun
> 
> - /autorun - Makes a silent registry check. If registry is good then a backup is made and it quits. If registry is bad then scanreg is set to make a restore at next boot and the machine is restarted.

 Note that in Windows Me it is also possible to use SCANREG inside a DOS prompt, it will then restart to commit the changes. One can also do it directly from DOS by booting from a [Windows Me startup disk](http://support.microsoft.com/kb/267287 "How to Create a Startup Disk in Windows Me [Q267287]").  
  
 Note there is a file called **Scanreg.ini**, which resides in the Windows directory. It contains parameters for how the Registry Checker should perform it's backup operation.  
  
<table border="1"><tr><th>Scanreg.ini Option</th><th>Description</th></tr><tr><td>Backup=</td><td>A value of 1 (default) causes a backup to be made once a day if the computer is started.  
 A value of 0 disables automatic backups to be made.</td></tr><tr><td>Optimize=</td><td>A value of 1 (default) causes it to automatically optimize your current registry if required.  
 A value of 0 disables optimizing of the registry.</td></tr><tr><td>MaxBackupCopies=</td><td>A value of 5 (default) causes it to save the last 5 registry backups (max 99).</td></tr><tr><td>BackupDirectory=</td><td>Have no value by default and causes registry backups to be saved in the Windows\\Sysbckup folder.  
 To change the location of where to make backups, change the value to fx. **c:\\registry\\backups**</td></tr><tr><td valign="top">Files=</td><td>Have no value by default and causes only system files to be saved.  
 To specify additional files add one or more Files= entries using this syntax: <div class="quote">Files=&lt;folder code&gt;,&lt;file name&gt;,&lt;file name&gt;...</div> The following folder codes can be used:
- 10 - Windows folder
- 11 - Windows\\System folder
- 30 - Root folder (C:\\)
- 31 - Root host folder (C:\\)
 
 Ex.: <div class="quote"> Files=11,actmovie.exe </div></td></tr></table>

  
 More Info [MS KB184023](http://support.microsoft.com/kb/184023 "Command-Line Switches for the Registry Checker Tool [Q184023]")  
 More Info [MS KB183603](http://support.microsoft.com/kb/183603 "How to Customize Registry Checker Tool Settings [Q183603]")  
 More Info [MS KB183887](http://support.microsoft.com/kb/183887 "Description of the Windows Registry Checker Tool (Scanreg.exe) [Q183887]")  
 More Info [MS KB198864](http://support.microsoft.com/kb/198864 "Registry Is Not Backed Up Automatically at Startup [Q198864]")  
 More Info [MS KB201655](http://support.microsoft.com/kb/201655 "Error Message: You Have Restored a Good Registry... [Q201655]")  
 More Info [MS KB245147](http://support.microsoft.com/kb/245147 "Scanreg.exe Does Not Back Up User.dat Files When Using User Profiles [Q245147]")  