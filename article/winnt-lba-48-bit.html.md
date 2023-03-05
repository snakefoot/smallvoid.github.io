---
title: 'Enable support for hard disk above 137 GByte'
date: '2002-10-12T22:17:24+02:00'
status: publish
permalink: /article/winnt-lba-48-bit.html
author: Snakefoot
excerpt: 'Things to be aware of when using a hard disk larger than 137 gigabyte.'
type: post
id: 398
category:
    - Tips
    - Tips
tag:
    - hard-disk-drive
    - logical-block-addressing
post_format: []
tags:
    - 'logical-block-addressing,hard-disk-drive'
---
If using an Hard disk drive (HDD) larger than 137 gigabyte (GB), then one might not have access to the entire HDD. To use such a large HDD then one needs an 48 Bit LBA (Logical Block Addressing) ready system:

- It requires a motherboard (or disc-controller) BIOS that supports 48 Bit LBA 
  - Check with the manufacture of the motherboard (or disc-controller) to confirm it supports 48 Bit LBA
- It requires that Windows 2000/XP supports 48 Bit LBA 
  - Check that one is at least using Windows 2000 SP3 or Windows XP SP1
 
 Note Windows 2000 is a little tricky, as it doesn't support 48 Bit LBA in the text-mode install (Even if having slipstreamed SP3+), and will not recognize more than 137 GByte of the HDD.  
 If trying to install Windows 2000 and it writes data beyond the 137 GByte limit (Independent of partitions), then it will start to trash the beginning of the first partition. To avoid this do the following:
1. Install Windows 2000 on a partition within the first 137 GByte.
2. Right after the first login then start the registry editor and create this registry key:
 > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\atapi \\Parameters\]  
 >  EnableBigLba = 1
 
 Note be careful when installing/using other operating systems that doesn't support 48 Bit LBA (Ex. Windows 98, Windows 2000 or Windows XP without SP1) on a HDD larger than 137 GByte, as they will trash the data on the HDD and give errors like:
> *C: is corrupt or unreadable  
>   
>  C:\\ path is inaccessible. the file or folder is corrupt and unreadable  
>   
>  The file or directory C:\\[$MFT](/article/winnt-ntfs-mft.html) is corrupt and unreadable. please run the chkdsk utility*

 More Info [MS KB303013](http://support.microsoft.com/kb/303013 "How to Enable 48-bit Logical Block Addressing Support for ATAPI Disk Drives in Windows XP [Q303013]")  
 More Info [MS KB305098](http://support.microsoft.com/kb/305098 "48-bit LBA Support for ATAPI Disk Drives in Windows 2000 [Q305098]")  
 More Info [MS KB314695](http://support.microsoft.com/kb/314695 "Mirrored Drives Larger Than 137 GB Perform Slowly [Q314695]") (ATAPI.SYS is updated in Win2k SP3)  
 More Info [MS KB331958](http://support.microsoft.com/kb/331958 "Hard Disk May Become Corrupted When Entering Standby or Hibernation or When Writing a Memory Dump [Q331958]") (ATAPI.SYS Update for WinXP SP1)  
  
 Credits [jsifaq.com](http://www.jsifaq.com/)