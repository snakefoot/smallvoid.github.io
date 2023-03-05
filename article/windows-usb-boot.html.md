---
title: 'Creating a bootable USB stick'
date: '2007-12-08T04:20:20+01:00'
status: publish
permalink: /article/windows-usb-boot.html
author: Snakefoot
excerpt: 'How to make a DOS bootdisk on a USB pen drive.'
type: post
id: 762
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - BIOS
    - bootdisk
    - system-recovery
    - usb
    - usb-stick
post_format: []
tags:
    - 'usb,usb-stick,bootdisk,bios,system-recovery'
---
It is possible to boot from a USB pen- / stick- / flash- / thumb-drive, which can be useful for different things:

- The USB stick can be used for system recovery, as it can contain lots of tools and can store files one might want to recover from the system.
- The USB stick can be used for motherboard BIOS flash, as not all computers has a floppy drive or can find BIOS flashing tools compatible with ex. Vista

##### Installing/recovering Windows from USB stick

 There different tools available that can help in preparing the USB stick:
- [Microsoft ISO tool](http://store.microsoft.com/help/ISO-Tool) - To Create a bootable DVD or USB flash drive from an ISO file. More Info [Wudt.codeplex.com](http://wudt.codeplex.com/ "Windows7-USB-DVD-tool.exe")
- [Download Windows Vista/7 Recovery Disk ISO](http://neosmart.net/wiki/display/EBCD/Recovering%20the%20Vista%20Bootloader%20from%20the%20DVD)
- [WinToFlash](http://wintoflash.com/home/en/) -Transfer your favorite rescue/live CD to a bootable USB flash device.
- [UNetbootin](http://unetbootin.sourceforge.net/) - Create bootable Live USB drive for your favorite Linux distribution. It runs on both Windows and Linux.
 
 Related [Preinstalled Environment for emergency recovery](/article/winnt-preinstalled-environment.html)  
 Related [Create Windows 7 Repair disk on USB stick](/article/winnt-usb-repair-disk.html)  
##### Booting into DOS using USB stick

 To flash the motherboard BIOS, then one is usually required to boot into DOS to run the AwdFlash.exe utility. The [HP USB Disk Storage Format Tool](http://www.softpedia.com/get/System/Hard-Disk-Utils/HP-USB-Disk-Storage-Format-Tool.shtml) comes to the rescue as it allows one to easily format an USB stick, so it will work as a [DOS bootdisk](/article/dos-bootdisk.html). One just have to check "using DOS system files located at" and point it to a location where the [3 critical files](http://smallvoid.orgfree.com/?file=bootdisk.zip) for a DOS boot disk **Msdos.sys**, **Io.sys** and **Command.com** resides.  
  
##### Booting from USB stick

 The hardest part is actually to figure out how to tell the motherboard that it should boot from the USB stick instead of the CD-ROM or hard disk. - For the Intel P35 Motherboard one has to select "Advanced BIOS features" and select "Hard disk boot priority", where the USB pen should be listed, and then one can use Page-Up and Down to change the boot selection order (First I thought it was the "First boot device" one should change, but neither USB-FDD, USB-ZIP or USB-CDROM worked).