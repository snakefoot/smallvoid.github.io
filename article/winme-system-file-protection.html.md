---
title: 'Using the System File Protection in Windows Me'
date: '2003-01-10T01:02:04+01:00'
status: publish
permalink: /article/winme-system-file-protection.html
author: Snakefoot
excerpt: 'System File Protection makes sure that critical system files are not overwritten.'
type: post
id: 178
category:
    - Troubleshoot
tag:
    - system-file-protection
post_format: []
tags:
    - system-file-protection
---
In an attempt to become more user friendly Microsoft decided that the user shouldn't be bothered at all by 3rd party applications(Or the user himself) overwriting / deleting system files.  
  
 This lead to the creating of the System File Protection, which provides constant system file checking. This is done by having a process constantly running in the background, and automatically checking when critical files are modified, deleted, or renamed. The list of critical files monitored is contained in this text-file:

> Windows\\System\\Sfp\\Sfpdb.sfp

 If the new version of the file doesn't match the identification specified in the System.cat file, then the new file is moved to Windows/System/Sfp/Archive, and the original file is restored. All the actions of System File Protection are logged in this textfile:
 > Windows\\System\\Sfp\\Sfplog.txt

 Note to restore a single file inside Windows Me use the System Configuration tool (msconfig.exe) and press the "Extract File"-button. It is possible to point it to a different directory to restore files from. This could f.ex. be a directory containing the install cab files for the Internet Explorer.  
  
 Note if needing to overwrite a protected file then use a DOS bootdisk and overwrite the file outside Windows (Though if the file is changed later then it will be restored). If needing to use a certain version of a DLL with an 3rd party application then place the "special" DLL in the same directory as the 3rd party application.  
  
 Note it is possible to disable System File Protection but it is NOT recommended. Stop the application StateMgr.exe from loading at startup using Msconfig or similar. Though this will also disable the [System Restore](/article/winme-system-restore.html) along with the Microsoft HelpSystem.  
  
 Related [Display System file protection notifications](/article/winme-sfp-notification.html)  
  
 More Info [MS KB253571](http://support.microsoft.com/kb/253571 "Description of the System File Protection Feature [Q253571]")  
 More Info [MS KB260195](http://support.microsoft.com/kb/260195 "Description of the Sfplog.txt File [Q260195]")  
 More Info [MS KB265371](http://support.microsoft.com/kb/265371 "How to Extract and Replace a Protected File in Windows Me [Q265371]")  
 More Info [MS KB266714](http://support.microsoft.com/kb/266714 "SFP Cannot Function When System.cat File Is Corrupt or Missing [Q266714]")  
 More Info [MS KB267282](http://support.microsoft.com/kb/267282 "A Description of the Sfpdb.sfp Database File [Q267282]")  
 More Info [MS KB274090](http://support.microsoft.com/kb/274090 "System File Checker Is Not Included in Windows Millennium Edition [Q274090]")  
 More Info [MS KB275156](http://support.microsoft.com/kb/275156 "How to Determine if a File Is Protected by System File Protection [Q275156]")  