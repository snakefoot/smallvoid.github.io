---
title: 'Create Windows 7 System Repair disk on USB stick'
date: '2011-01-18T00:41:47+01:00'
status: publish
permalink: /article/winnt-usb-repair-disk.html
author: Snakefoot
excerpt: 'How to create a bootable Windows 7 System Repair disc on an USB pen drive.'
type: post
id: 829
category:
    - Troubleshoot
tag:
    - bootdisk
    - system-recovery
    - usb
    - usb-stick
    - windows-recovery-environment
post_format: []
tags:
    - 'windows-recovery-environment,system-recovery,usb,usb-stick,bootdisk'
---
Windows 7 includes an utility to **Create a system repair disc** that includes [Windows Recovery Environment](/article/winnt-recovery-environment.html).  
  
 The utility can only write to a CD/DVD, so extra steps have to be performed to create an USB stick:

1. Use the utility to **Create a system repair disc** and burn it to a CD/DVD
2. Prepare an USB stick to be bootable: 
  1. Insert the USB stick, and let Windows discover the removable disk
  2. Open an [Elevated Command Prompt](/article/winnt-user-account-protection.html#ELEVATED).
  3. Launch the command line disk partitioning utility with this command:
     > diskpart
  4. List the available disks on the computer:
     > list disk
  5. Choose the removable USB disk ("?" should be the disk number from the list):
     > select disk ?
  6. Clean all existing partitions:
     > clean
  7. Create new partition:
     > create partition primary
  8. Mark partition as active:
     > active
  9. Format new partition:
     > format fs=fat32
3. Copy the files from the burned CD/DVD to the now prepared USB stick
 
 More Info [Create a system repair disc](http://windows.microsoft.com/en-US/windows7/Create-a-system-repair-disc)  
  
 Related [Creating a Recovery Disk on an USB stick](/article/windows-usb-boot.html)  
  
 Credits [MultiBooters.co.uk](http://www.multibooters.co.uk/articles/windows_seven.html#winre)