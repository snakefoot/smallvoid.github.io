---
title: 'No boot device found or available'
date: '2007-10-29T21:11:32+01:00'
status: publish
permalink: /article/no-boot-device-found.html
author: Snakefoot
excerpt: 'Computer cannot start if no proper boot device exists, or if the active boot device fails.'
type: post
id: 752
category:
    - Tips
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - boot-manager
    - hard-disk-drive
    - partition
    - system-recovery
post_format: []
tags:
    - 'boot-manager,hard-disk-drive,partition,system-recovery'
---
When the computer starts then it tries to figure out which device to boot from (Hard-disk, cdrom, dvd, usb, flash, floppy, etc.). If no device is found or if a faulty boot device is used, then one of the following messages can be shown:

> Invalid boot device  
>   
>  No boot device found  
>   
>  No boot device available  
>   
>  Unable to find boot device. Select proper boot device or insert boot media  
>   
>  BOOTMGR is missing. Press Ctrl+Alt+Del to restart

 There can be different causes for this problem:
- **Disk a have been left in a removable drive:**  
   Usually caused by having inserted a disk in the floppy drive or the CD-ROM drive or attaching an USB flash drive. Just remove the disk from the drive, and it should be solved. More Info [MS KB812492](http://support.microsoft.com/kb/812492 "Error message when you start your computer with a non-system disk [Q812492]")
- **Trying to boot from a hard disk that is no longer recognized as boot device:**  
   One should verify that hard disk cables are properly attached and that the hard disk is being detected properly by the system.  
   If having added a new hard disk, then one should make sure that the disk controller doesn't attempt to boot from the new hard disk.  
   If having reset the motherboard BIOS configuration, then one should check that the primary boot device is configured properly.
- **Boot partition is not active partition:**  
   If having been working with partition tools (Like Disk Management or Fdisk), then one might have removed the Active Partition setting from the boot partition. 
  - Vista - Use [Windows Recovery Environment](/article/winnt-recovery-environment.html) and perform a "Startup Repair".
  - Win2k / XP / Win2k3 - Use [Recovery Console](/article/winnt-recovery-console.html) and run fixboot
  - Win9x / DOS - Use a partition configuration tool like [Fdisk](/article/fdisk.html) to set the active boot partition.
   
   More Info [MS KB315261](http://support.microsoft.com/kb/315261 "The computer does not start after you change the active partition by using the Disk Management tool [Q315261]")
- **Trying to boot from a CD / DVD to install the operating system:**  
   Just like when booting from a hard disk, then one must ensure that the motherboard BIOS actually recognizes the CD / DVD-drive. If not then check the power- and data-cables to the CD / DVD drive.  
    
   If the motherboard BIOS recognizes the CD / DVD drive, then one must configure the boot device priority in the motherboard BIOS so the CD / DVD drive has the highest priority. This will ensure that it will not try to boot from other devices before booting from the CD / DVD drive.
 
 Related [Inaccessible boot device BSOD](/article/winnt-inaccessible-boot-device.html)  
 Related [Restore boot manager when NTLDR is missing](/article/winnt-restore-ntldr.html)  
 Related [Restore bootmgr when it is missing or compressed](/article/winnt-bootmgr-missing.html)  