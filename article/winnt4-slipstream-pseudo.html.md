---
title: 'Pseudo slipstream in Windows NT4'
date: '2004-10-13T06:22:12+02:00'
status: publish
permalink: /article/winnt4-slipstream-pseudo.html
author: Snakefoot
excerpt: 'Windows NT4 does not support slip streaming, but it is possible to make a few changes.'
type: post
id: 488
category:
    - 'Install CD'
tag:
    - slipstream
    - windows-install
post_format: []
tags:
    - 'slipstream,windows-install'
---
The slipstreaming of service packs is not available with WinNT4, as it was first introduced with Win2k. But it is still possible to do some tricks:

- Update these files on the install-image with files from the service pack (SP4+), as it will enable AGP support, remove 8gb limitation etc. > atapi.sys  
  >  fastfat.sys  
  >  gdi32.dll  
  >  hal.dll  
  >  hal486c.dll  
  >  halapic.dll  
  >  halast.dll  
  >  halcbus.dll  
  >  halcbusm.dll  
  >  halmca.dll  
  >  halmps.dll  
  >  halmpsm.dll  
  >  halncr.dll  
  >  haloli.dll  
  >  halsp.dll  
  >  halwyse7.dll  
  >  kernel32.dll  
  >  ndis.sys  
  >  ntdll.dll  
  >  ntkrnlmp.exe  
  >  ntoskrnl.exe  
  >  SETUPDD.SYS  
  >  tcpcfg.dll  
  >  user32.dll  
  >  win32k.sys  
  >  winsrv.dll
- Install the service pack unattended (SP4+) 
  - Place the service-pack file in this directory:
    > X:\\i386\\$OEM$\\SP4
  - Create a text file **CMDLINES.TXT** in this directory:
    > X:\\i386\\$OEM$
  - Open the text file **CMDLINES.TXT** and add these lines:
    > \[Commands\]  
    >  ".\\sp4\\sp4i386.exe -z -u"
   
   More Info [MS KB168814](http://support.microsoft.com/kb/168814 "INFO: Installing Windows NT 4.0 Service Packs During Unattended Installation [Q168814]")
- Make a shared directory with the original WinNT4 install files and extract the contents of the service pack to this directory. Then [use the shared directory](/article/winnt-source-path-install.html) when adding components (after install), so you don't have to apply the service pack for every change.
 
 Note it is possible to create a bootable WinNT4 CD by using the [boot sector from Win2k](/article/win2k-install-cd-boot-sector.html).