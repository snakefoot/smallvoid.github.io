---
title: Dynaload
date: '2000-01-01T14:36:23+01:00'
status: publish
permalink: /article/dynaload.html
author: Snakefoot
excerpt: 'Allows one to load device drivers from the command prompt instead of using the config.sys.'
type: post
id: 79
category:
    - Utilities
tag:
    - cdrom-drive
    - device-driver
post_format: []
tags:
    - 'device-driver,cdrom-drive'
---
[Dynaload](http://smallvoid.orgfree.com/?file=dynaload.zip) was released with PC-DOS 7.0 by IBM. It can load device drivers (sys-files like your cd-rom driver) into memory from the command prompt, without requiring a reboot.  
  
 This utility can be used to make a batch file which loads the CD-ROM drivers, so if they haven't been loaded then you can load them on demand using the batch without needing to reboot.  
  
 It can also be used in the [DOSSTART.BAT](/article/win9x-dosstart.html) which is executed by Win9x when doing "Exit To DOS", so one don't need to have the DOS CD-ROM drivers loaded in the CONFIG.SYS anymore.  
  
 Note Creative have created a similar tool called [Ctload](http://smallvoid.orgfree.com/?file=ctload.zip).