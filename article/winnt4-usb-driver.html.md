---
title: 'USB driver for Windows NT4'
date: '2006-02-18T14:08:55+01:00'
status: publish
permalink: /article/winnt4-usb-driver.html
author: Snakefoot
excerpt: 'Open access to USB devices in Windows NT4 by installing these USB drivers.'
type: post
id: 491
category:
    - Utilities
tag:
    - removable-storage-devices
    - usb
post_format: []
tags:
    - 'usb,removable-storage-devices'
---
Windows NT 4.0 doesn't have native USB support, but with these free [USB drivers](http://us.geocities.com/mypublic99/ "Woodhead") it is possible to use USB-keyboard, -mice, -flash disk with that old horse of an operating system.

- Dell have also created a set of [USB drivers for NT4](http://ftp1.us.dell.com/utility/R62200.EXE), which have been reported to be working well with many USB devices. The drivers can also be used even if not having a Dell computer.
 
 Note when attaching mass storage devices (Like USB-drives), then one might have to use Disk Management to assign a drive letter manually.  
  
 Note there exists hardware that can convert USB to PS/2, so if the problem is attaching an USB keyboard or mouse to a computer running NT4, then it can be solved by using a hardware converter instead of trying to enable USB on Windows NT.  
  
 Note these drivers are unsupported, so be careful when applying them to a mission critical system. More Info [MS KB196661](http://support.microsoft.com/kb/196661 "Windows NT 4.0 does not support Universal Serial Bus [Q196661]")