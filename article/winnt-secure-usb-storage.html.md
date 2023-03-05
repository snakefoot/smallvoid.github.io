---
title: 'Restrict access to the USB storage devices'
date: '2005-10-26T22:19:08+02:00'
status: publish
permalink: /article/winnt-secure-usb-storage.html
author: Snakefoot
excerpt: 'USB makes it easy to attach a storage device and steal valuable data from a computer.'
type: post
id: 456
category:
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - removable-storage-devices
    - usb
    - usb-stick
post_format: []
tags:
    - 'usb,usb-stick,removable-storage-devices'
---
The ability to use USB stick and HDD makes it easy to transfer files from one computer to another. By default it is possible for any user to attach such an USB storage device and start transfering data.  
  
 Restrict access for installing new USB storage devices by changing the [permissions](/article/ntfs-access-control.html) of these files:

- %SystemRoot%\\Inf\\Usbstor.pnf
- %SystemRoot%\\Inf\\Usbstor.inf
 
 Restrict access to any USB storage device (also existing) for any user by [disabling the driver](/article/winnt-services-regedit.html):
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\UsbStor\]  
>  Start = 4  
>   
>  More Info [MS KB823732](http://support.microsoft.com/kb/823732 "How to disable the use of USB storage devices [Q823732]")

 Restrict write access to any USB storage device for any user (WinXP SP2+):
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\StorageDevicePolicies\]  
>  WriteProtect = 1  
>   
>  More Info [Changes to Functionality in Microsoft Windows XP Service Pack 2](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/sp2otech.mspx)

 Related [Control access to removable storage devices in Vista](/article/winnt-removable-storage.html).  