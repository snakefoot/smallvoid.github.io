---
title: 'Configure drive letter for the CD-ROM Drive'
date: '2003-11-22T23:58:22+01:00'
status: publish
permalink: /article/assign-drive-letter.html
author: Snakefoot
excerpt: 'Assign specific drive letters for removable drives.'
type: post
id: 113
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - cdrom-drive
    - drive-letter
    - dvd-drive
    - removable-storage-devices
    - usb
    - usb-stick
post_format: []
tags:
    - 'cdrom-drive,dvd-drive,usb,usb-stick,drive-letter,removable-storage-devices'
---
It is quite important that the drive letter for the CD Drives remains static, as many applications and games installed from a CD Drive expects to find its files on the same drive letter as when they were installed.  
 In Win9x/Me the drive letter for the CD Drives are by default assigned dynamically, so if a HDD partition is added or removed, then the drive letter for the CD Drives will change.  
 In WinNT+ the drive letter for the CD Drives are static, but if updating drivers for the disk controller or similar, so the CD Drives are redetected then the "new" CD Drives might get new drive letters.  
  
 To change the drive letter for CD Drives in Win9x/Me:
1. Right click **My Computer** and select **Properties**
2. Select the tab **Device Manager**
3. Right click your CD-ROM drive and select **Properties**
4. Select the tab **Settings**
5. In the **Reserved Drive Letters** set **Start Drive Letter** and **End Drive Letter** to the letter you want.
 
 More Info [MS KB121244](http://support.microsoft.com/kb/121244 "How to Change the Drive Letter of a CD-ROM Drive [Q121244]")  
  
 To change the drive letter for CD Drives in WinNT4:
1. Go to the **Start** -&gt; **Programs** -&gt; **Administrative Tools (Common)** -&gt; **Disk Administrator**
2. Right click your CD-ROM drive and select the option **Assign Drive Letter...**
3. Change **Assign a drive letter** to the wanted drive letter and press **Ok**
4. A popup will tell you that the drive letter will change just press **Ok**. (If an application is currently using the drive letter the change will take effect the next boot).
 
 More Info [MS KB142635](http://support.microsoft.com/kb/142635 "Cannot Change the Drive Letter of Removable Drives [Q142635]")  
  
 To change the drive letter for CD Drives in Win2k/XP:
1. Right click **My Computer** and select **Manage**
2. Select **Disk Management** (Below the Storage-node)
3. Right Click your CDROM drive and select **Change Drive Letter and Path...**
4. Select the drive letter it has now and press **Edit** (If it doesn't have a drive letter press Add)
5. Change **Assign a drive letter** to the wanted drive letter and press **Ok**
6. A popup will tell you that the drive letter will change just press **Ok**. (If an application is currently using the drive letter the change will take effect the next boot).
 
 More Info [MS KB223188](http://support.microsoft.com/kb/223188 "How to restore the system/boot drive letter in Windows [Q223188]")  
 More Info [MS KB307844](http://support.microsoft.com/kb/307844 "HOW TO: Change Drive Letter Assignments in Windows XP [Q307844]")  
  
 Note the WinNT+ Disk Administration is also capable of changing the drive letter for HDD partitions. Just right click the HDD partition instead of the CDROM drive. It is also possible to remove the assignment of drive letter thus hiding the HDD partition, which can be useful in a dual boot environment.  
  
 Note in Win9x/Me there is a tool [Letter Assigner](/article/win9x-letter-assigner.html), which allow one to also change the drive letters for HDD partitions.  
  
 Note if wanting to configure USB devices so they maintain their drive letters, then [USB Drive Letter Manager](http://www.uwe-sieber.de/usbdlm_e.html) might do want you want. It works for Windows 2000/XP/Vista.  