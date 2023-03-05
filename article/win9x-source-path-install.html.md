---
title: 'Change the source path for the install files in Windows 9x'
date: '2000-01-01T23:41:19+01:00'
status: publish
permalink: /article/win9x-source-path-install.html
author: Snakefoot
excerpt: 'Configure the path to the location of the install files whether on CD-ROM or HDD.'
type: post
id: 158
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - cdrom-drive
    - hard-disk-drive
    - install-path
post_format: []
tags:
    - 'hard-disk-drive,cdrom-drive,install-path'
---
The hard disk have become so big, that the Windows install CD can easily fit on the hard disk. This is rather convenient as one doesn't have to worry about finding the install CD every time one touches the Windows install, or getting the install CD scratched by having it lying around all the time.  
  
 To copy the install CD to the hard disk:

1. Copy the Win9x directory from the install cd to the following directory:
   > C:\\Install\\Win9x
2. Change the following registry setting to configure the new install path:
   > \[HKEY\_LOCAL\_MACHINE\\ Software\\ Microsoft\\ Windows\\ CurrentVersion\\ Setup\]  
   >  SourcePath="C:\\Install\\Win9x"
 
 Note the next one has to perform an install of Windows, then perform the install from the hard disk, so one doesn't have to worry about changing the registry.  
  
 More Info [MS KB131652](http://support.microsoft.com/kb/131652 "How to Change the Setup Source Path in Windows [Q131652]")  
 More Info [MS KB266735](http://support.microsoft.com/kb/266735 "How to Move Windows Me Installation (.cab) Files to Another Drive [Q266735]")  
  
 Related [Configure Drive Letter for the CD-ROM drive](/article/assign-drive-letter.html)  