---
title: 'Long-Filename Backup Tool'
date: '2000-01-01T13:59:34+01:00'
status: publish
permalink: /article/long-filename-backup.html
author: Snakefoot
excerpt: 'Backup and restore long filenames in DOS. Useful if working with DOS tools not supporting long filenames.'
type: post
id: 75
category:
    - Utilities
tag:
    - backup
    - doslfn
    - lfntools
    - long-filenames
    - restore
post_format: []
tags:
    - 'long-filenames,backup,restore,doslfn,lfntools'
---
When working with long filenames in DOS the long filenames are lost because the long filename has to be updated in the VFAT and standard DOS utilities can only work on the FAT.  
 Microsoft have create the utility [W95lfnb.exe](http://www.microsoft.com/windows95/downloads/contents/WUAdminTools/S_WUManagementTools/W95LongFile/Default.asp), which is able to save the long filenames stored in the VFAT, so you can restore the long filenames again after you have worked with the files in DOS.  
  
 This makes it possible to backup Windows from DOS without rendering it useless:

1. Backup the long filenames on your entire C-Drive using W95lfnb.exe
2. Backup the files (including the long filename backup) into an archive using an util like PKZIP, RAR, ACE, ARJ etc.
 
 When your Windows have gone bad then you can restore within minutes:
1. Delete the bad Windows installation
2. Restore the files from the archive using an util like PKZIP, RAR, ACE, ARJ etc.
3. Restore the long filenames from the long filename backup
 
 Note if you have the money or the skills then this operation can be done more easily with a disk image tool like Ghost.  
  
 Note it is possible to perform backup of long filenames (LFN) directly by using [DOSLFN](http://smallvoid.orgfree.com/?file=doslfn-0.40a.zip "DOSLFN v.04a") ([Download Mirror](http://www.uwe-sieber.de/util_e.html)), along with [PKZIP for DOS V2.50](http://www.pkware.com/). DOSLFN implements the Windows 95 LFN API under DOS.  
  
 Note [LFN Tools](http://lfntools.sourceforge.net/) is a small collection of tools that allows one to work with long filenames in pure DOS.