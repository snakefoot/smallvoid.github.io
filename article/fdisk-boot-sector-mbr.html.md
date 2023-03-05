---
title: 'Using FDISK to remove a boot-sector virus'
date: '2000-01-01T09:52:45+01:00'
status: publish
permalink: /article/fdisk-boot-sector-mbr.html
author: Snakefoot
excerpt: 'How to rewrite the master boot record with fdisk to disable a boot-sector virus.'
type: post
id: 61
category:
    - Tips
tag:
    - boot-sector
    - fdisk
    - master-boot-record
    - mbr
    - virus
post_format: []
tags:
    - 'fdisk,master-boot-record,mbr,boot-sector,virus'
---
If you for reason have gotten a boot-sector virus on your hands, then the virus is loaded when booting and the antivirus program won't start.  
  
 The best thing you can do is to get hold of a bootable floppy disk with the newest antivirus program loaded and make it do its job.  
  
 If you don't have a bootable floppy disk, then there is another way to damage the bootsector virus so it doesn't load at boot time, allowing you to run your antivirus program. It is to rewrite the Master Boot Record(MBR) bootstrap using FDISK, though it is NOT recommended since :

- If running encryption or other 3rd party tools which might have changed the MBR bootstrap. FDISk will instead ruin the MBR and one will loose access to the data.
- If the actual virus have moved the MBR partition table. FDISK will then loose the connection to the partition table leaving one with no partitions. (Requiring one to rebuild the partition table manually by using a disk editor)
- If the actual virus is running on-the-fly encryption/decryption of the files. FDISK will remove the virus but also the encryption/decryption algorithm in the virus leaving one with useless encrypted data.
 
 Credits [Computer Knowlegde](http://www.cknow.com/vtutor/FDISKMBR.html)  
  
 But if one still dare to try it. : - Make sure you are not running any programs at start up, as they might also be infected.
  > move C:\\autoexec.bat C:\\autoexec.old  
  > move C:\\config.sys C:\\config.old
- If using MS DOS 7 (Win9x), make sure to press F8 so you don't enter Windows, but boot into Clean DOS
- Then use FDISK to rewrite the master boot record > FDISK /MBR
- Reboot right after and now you should have loaded DOS without having the virus loaded to memory. Thus allowing you to start the antivirus program and remove the virus completely.
 
 Another solution is to delete the infected partition using FDISK and create it again. Though with the side effect that you will loose all data on that partition.  
  
 More Info [MS KB69013](http://support.microsoft.com/kb/69013 "FDISK /MBR Rewrites the Master Boot Record [Q69013]")  
 More Info [MS KB140418](http://support.microsoft.com/kb/140418 "Detailed Explanation of FAT Boot Sector [Q140418]")  