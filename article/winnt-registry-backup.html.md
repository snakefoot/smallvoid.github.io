---
title: 'Backup and restore the Windows NT registry database'
date: '2003-03-01T01:43:43+01:00'
status: publish
permalink: /article/winnt-registry-backup.html
author: Snakefoot
excerpt: 'Before making changes to the registry database, then it can be a very good idea to make a backup first.'
type: post
id: 472
category:
    - Utilities
    - Utilities
    - Utilities
tag:
    - registry
post_format: []
tags:
    - registry
---
Microsoft released with the Windows 2000 resource kit the following two utilities:

- [RegRest](http://smallvoid.orgfree.com/?file=regrest.zip)
- [RegBack](http://smallvoid.orgfree.com/?file=regback.zip)
 
 They allow one to backup and restore the registry, which also can be used to shrink/compress the registry files. The system registry (Software, System, Sam) and the user registry (Ntuser.dat) can grow large over time as software and hardware is installed and uninstalled.  
  
 To backup the current system and user profile to C:\\Backup (Remember to have created the directory):
 > Regback C:\\Backup

 This will restore a backup from C:\\Backup and files being replaced are placed in C:\\Backup.old (Remember to have created the directory):
 > Regrest C:\\Backup C:\\Backup.old

 The restore just renames the file so both the new, backup and destination must be on the same drive. One can also do the restore the registry using the [recovery console](/article/winnt-recovery-console-registry-restore.html) as the Regback saves the backup in the proper registry file format.  
  
 Note if one don't like command line tools then one can try this very userfriendly utility called [EruNT](http://www.larshederer.homepage.t-online.de/).  
  
 More Info [MS KB318149](http://support.microsoft.com/kb/318149 "How to Maintain Current Registry Backups in Windows NT 4.0 and Windows 2000 [Q318149]")