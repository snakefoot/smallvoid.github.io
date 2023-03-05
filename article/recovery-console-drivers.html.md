---
title: 'Include 3rd party controller drivers in the recovery console'
date: '2003-03-01T03:01:27+01:00'
status: publish
permalink: /article/recovery-console-drivers.html
author: Snakefoot
excerpt: 'Modify the Recovery Console installation so it will load 3rd party drivers for your disk controller.'
type: post
id: 258
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - recovery-console
post_format: []
tags:
    - recovery-console
---
The Recovery Console cannot access a HDD attached to a 3rd party controller, which is not support by the WinNT default drivers. If one don't press F6 and provide the 3rd party drivers on a floppy it will present a BSOD with INACCESSIBLE BOOT DEVICE.  
  
 It can be a hassle to always have a floppy disk around and some machines don't even have a floppy drive. To solve this one can try to add the 3rd party drivers to the recovery console installation.

1. [Install the Recovery Console](/article/winnt-recovery-console.html#INSTALL)
2. Go to the %systemroot%\\cmdcons
3. Copy your driver raidcntr.sys to %systemroot%\\cmdcons
4. Make a copy of the %systemroot%\\cmdcons\\txtsetup.sif for backup in case something goes wrong
5. Open the %systemroot%\\cmdcons\\txtsetup.sif with a text editor
6. Search for the text "ultra66" and you should find:
> ultra66.sys = 1,,,,,,3\_,4,1
   Make a copy of the line and place it below and change ultra.sys to raidcntr.sys :  
> raidcntr.sys = 1,,,,,,3\_,4,1
7. Search again for the text "ultra66" and you should find:
> PCI\\VEN\_105A&amp;DEV\_4D38 = "ultra66"
  
   Now open the TXTSETUP.OEM which comes with your driver raidcntr.sys and find the Hardware Id of your controller. Ex.:
> \[HardwareIds.scsi.raid\_win200\]  
>  id = "PCI\\VEN\_105A&amp;DEV\_0D30&amp;SUBSYS\_4D33105A","raidcntr"
  
   Create a new line under "ultra66"-line using the Hardware Id for your controller. Ex.
> PCI\\VEN\_105A&amp;DEV\_0D30&amp;SUBSYS\_4D33105A = "raidcntr"
8. Search again for the text "ultra66" and you should find:
   > ultra66 = ultra66.sys,4
  
   Make a copy of the line and change the ultra66 to raidcntr:
> raidcntr = raidcntr.sys,4
9. Search again for the text "ultra66" and you should find:
> ultra66 = "Promise Technology Inc. Ultra66 IDE Controller"
   Make a copy of the line and change the text to something you like:
> raidcntr = "My Personal RAID Controller"
10. Save the txtsetup.sif file and reboot and select the Recovery Console at the boot menu
 
 Note the above guidelines have worked fine with an A7V Onboard Promise Fasttrak100 controller.  
  
 Credits [Alan P. Kennedy](mailto:apkenned@removethis.telalink.net)