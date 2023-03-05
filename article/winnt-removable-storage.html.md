---
title: 'Restrict access to removable storage devices'
date: '2007-07-05T02:08:53+02:00'
status: publish
permalink: /article/winnt-removable-storage.html
author: Snakefoot
excerpt: 'Restrict access to removable storage devices to prevent misuse of them by an intruder.'
type: post
id: 655
category:
    - 'User Security'
tag:
    - access-control-list
    - removable-storage-devices
    - usb
    - usb-stick
    - user-account
post_format: []
tags:
    - 'usb,usb-stick,access-control-list,removable-storage-devices,user-account'
---
Microsoft Windows Vista enhances the access control to removable storage devices to include:

- CD and DVD Drives - All optical devices which includes HD-DVD and Blu-Ray drives.
- Floppy Drives - Floppy disk drives, including USB Floppy Disks.
- Removable Disks - Flash memory or hard drive based removable disks connected via USB or Firewire.
- Tape Drives - All classes of linear tape device.
- WPD Devices - Windows Portable Devices. Windows-based smartphones, media players, auxiliary displays and CE devices.
 
 The restriction to these devices can be controlled with group policies:
> User Configuration \\Administrative Templates \\System \\Removable Storage Access  
> Computer Configuration \\Administrative Templates \\System \\Removable Storage Access  
>   
> More Info [MS Technet : Group policies in Windows Vista/2008](http://technet2.microsoft.com/WindowsVista/en/library/2b8dc2fd-eafe-4c74-914c-ec101133feb41033.mspx)

 The restrictions can also be controlled through these registry settings:
 > \[HKEY\_LOCAL\_MACHINE \\Software \\Policies \\Microsoft \\Windows \\RemovableStorageDevices\]

 To make a restriction for a device-type, create a registry-key matching the device type:
 - CD and DVD Drives - **{53f56308-b6bf-11d0-94f2-00a0c91efb8b}**
- Floppy Drives - **{53f56311-b6bf-11d0-94f2-00a0c91efb8b}**
- Removable Disks - **{53f5630d-b6bf-11d0-94f2-00a0c91efb8b}**
- Tape Drives - **{53f5630b-b6bf-11d0-94f2-00a0c91efb8b}**
- WPD Devices needs two keys: 
  - **{6AC27878-A6FA-4155-BA85-F98F491D4F33}**
  - **{F33FDC04-D1AC-4E8E-9A30-19BBD4B108AE}**
 
 For each device type one can specify the type of restriction wanted with these DWORD values:
- **Deny\_Read** - Enabled = 1 / Disabled = 0
- **Deny\_Write** - Enabled = 1 / Disabled = 0
 
 Related [Restrict access to USB storage devices](/article/winnt-secure-usb-storage.html).  
  
 Credits [Sanx.org](http://sanx.org/)