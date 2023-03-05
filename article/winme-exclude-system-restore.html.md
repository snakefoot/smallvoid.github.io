---
title: 'Exclude file from System Restore in Windows Me'
date: '2003-06-21T19:52:58+02:00'
status: publish
permalink: /article/winme-exclude-system-restore.html
author: Snakefoot
excerpt: 'How to exclude a file so System Restore doesn''t monitor the file or perform backup.'
type: post
id: 108
category:
    - Troubleshoot
tag:
    - system-restore
post_format: []
tags:
    - system-restore
---
[System Restore](/article/winme-system-restore.html) monitors certain files, and when a file is changed, then a backup is made of the file and placed in C:\\\_Restore. This can lead to a large overhead in file operations if running applications that constantly updates files, which have an extension monitored by System Restore.  
  
 To exclude a file from System Restore:
1. Make a copy of C:\\Windows\\System\\Restore\\Filelist.xml and save it as Filelist.txt in the same folder
2. Edit Filelist.txt using notepad and add &lt;REC&gt;C:\\ThePath\\TheFile.ext&lt;REC&gt; to the &lt;Exclude&gt; section
3. Disable System Restore by opening Control Panel -&gt; System -&gt; Performance -&gt; File System -&gt; Troubleshooting and check "Disable System Restore"
4. Shutdown your system and boot using a [Windows Me startup disk](http://support.microsoft.com/kb/267287 "How to Create a Startup Disk in Windows Me [Q267287]") (To avoid the System File Protection)
5. In DOS browse to C:\\Windows\\System\\Restore
6. Rename Filelist.xml to Filelist.old (To make a backup)
7. Rename Filelist.txt to Filelist.xml
8. Take out the DOS floppy disk and reboot into Windows
9. Enable System Restore by unchecking "Disable System Restore"
10. Reboot your system and now it will rebuild the system restore control file vxdmon.dat from the new Filelist.xml
 
 Note one can remove the monitoring of Filelist.xml by System File Protection and System Restore, so one can easily change the file without needing to enter DOS. Though it can only be done in DOS or else it will rollback the changes.
1. Remove this entry from C:\\Windows\\System\\Restore\\Filelist.xml: (Avoid System Restore to include the file in Restore Points)
   > <REC>%WinSys%\restore\filelist.xml<REC>
2. Remove this entry from C:\\Windows\\System\\Sfp\\Sfpdb.sfp (Avoid System File Protection to restore the Filelist.xml if changed inside Windows)
   > C:\WINDOWS\SYSTEM\RESTORE\FILELIST.XML, 00000000, 00000000, SYSTEM.CAT
 
 Credits [Mike Maltby](mailto:Mike%20Maltby<mcmaltby@hotmail.com> "MS-MVP")