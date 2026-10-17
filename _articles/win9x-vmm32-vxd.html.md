---
title: 'The infamous VMM32.VXD tweak'
date: '2001-01-01T21:42:40+01:00'
permalink: /article/win9x-vmm32-vxd.html
author: Snakefoot
excerpt: 'VMM32.VXD is an archive of VXD files, and some have reported improved speed by extracting the VXD files.'
type: post
id: 96
categories:
    - windows-95_performance
    - windows-98_performance
    - windows-me_performance
tags:
    - conventional-memory
    - upper-memory-block
    - vmm32-vxd
---
The Windows\\system\\VMM32.VXD is a compressed file which contains a set of VxD (Virtual device Driver). The set of VxD-files are selected specifically for your machine so you shouldn't use the VMM32.VXD from a different computer.  
  
 The response time of Win9x should be increased by extracting the same set of VxD-files from the Win9x-CDROM's CAB-files and place them in the directory C:\\Windows\\System\\Vmm32. This will make Windows use the decompressed VxD-files instead of those placed in the VMM32.VXD.  
  
 You can see if a VxD file for a device is compressed into the VMM32.VXD, by starting the Device Manager and select Driver Details for a device, then you might see something like "C:\\Windows\\System\\vmm32.vxd (configmg.vxd)"  
  
 You can go to this registry key to find all the files which are inside the vmm32.vxd:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\VMM32Files\]

 Note everyone, who thinks that they know something, says that you will gain nothing from it and actually the compression of VxD files into VMM32.VXD was done to improve boot time. But at the same time there is a lot of people who have tried it and said the opposite.  
  
 Note the VMM32.VXD placed in the Win9x-CDROM's CAB-files is just a skeleton files and is not containing any VxD files.  
  
 Note the VMM32.VXD is usually loaded in the conventional memory area if no room is available in the UMB. If free conventional memory is important, then check [How to get a larger UMB](/article/upper-memory-block-umb.html).  
  
 Related [Use extract.exe to restore a system file](/article/win9x-extract-restore.html)  
 Related [Use of the System File Checker in Windows 98](/article/win98-sfc.html)  
 Related [Use of the System File Protection in Windows Me](/article/winme-system-file-protection.html)  
  
 More Info <a href="https://www.bing.com/search?q=KB%20174018%20Q174018" rel="nofollow" title="Description of the Windows 95 Startup Process [Q174018]">MS KB174018</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20194679%20Q194679" rel="nofollow" title="Error Message: VMM32.VXD Is Required to Run Windows... [Q194679]">MS KB194679</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20195164%20Q195164" rel="nofollow" title="Computer Stops Responding After You Press CTRL+ALT+DELETE [Q195164]">MS KB195164</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20296579%20Q296579" rel="nofollow" title="Error Message: Unpacking Vmm32.vxd, Library Invalid or Wrong Version ... [Q296579]">MS KB296579</a>  
  
 Credits [InfiniSource.com](http://www.infinisource.com/techfiles/vmm32.html)