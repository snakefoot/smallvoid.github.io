---
title: 'Convert FAT16 and FAT32 partition to NTFS'
date: '2002-12-31T00:45:31+01:00'
status: publish
permalink: /article/winnt-convert-ntfs.html
author: Snakefoot
excerpt: 'Description of the different issues that can arise when converting from FAT16 and FAT32 partitions to NTFS.'
type: post
id: 293
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - fat16
    - fat32
    - file-system
    - ntfs
post_format: []
tags:
    - 'ntfs,file-system,fat16,fat32'
---
To convert a partition open a command prompt and run this command where x is the drive-letter of the existing partition you want to convert:

> convert x: /fs:ntfs

 Note if the drive is in use, then the conversion will happen at next boot.  
  
 Note when converting in WinNT4/2k/XP the partition will get a [cluster size](/article/cluster-hard-disk-partition.html) of 512 bytes, which will give limited performance (4 KByte is usual the optimal) More Info [MS KB231756](http://support.microsoft.com/kb/231756 "The Convert.exe Tool Uses 512-Byte Clusters [Q231756]").  
  
 Note when converting in WinNT4/2k/XP the [MFT](/article/winnt-ntfs-mft.html) will become shattered all over the partition, causing low performance.  
  
 Note the [WinXP Deployment Tools](http://www.microsoft.com/windowsxp/downloads/updates/sp1/deploytools.mspx) can be be used to install on FAT16/FAT32 and then later convert to NTFS without getting a fragmented MFT and a 512 bytes cluster size. The utility **cvtarea** can reserve a continuous section of the partition which can be used by the MFT. The utility **oformat** can format the partition and [align FAT data clusters at the cluster size boundary](http://www.microsoft.com/whdc/system/winpreinst/ntfs-preinstall.mspx "NTFS Preinstallation and Windows XP") so the cluster size will become 4 KByte.  
  
 Note when converting a FAT16/FAT32 partition to NTFS, then [permissions](/article/ntfs-access-control.html) will not be configured. Therefore if converting the system drive, then one should make sure to configure the NTFS permissions after the conversion. More Info [MS KB266118](http://support.microsoft.com/kb/266118 "Overview of memory dump file options for Windows 2000, Windows XP, Windows Server 2003, Windows Vista, Windows Server 2008, Windows 7, and Windows Server 2008 R2 [Q266118]")  
  
 Note if the drive contains bad sectors (Use Chkdsk to see) then the conversion will fail, and it will require a full backup of the drive and then a NTFS format to do the conversion.  
  
 Note faster boot times will be gained when only having NTFS partitions, as Win2k/WinXP reads the entire File Allocation Table (FAT) for all FAT16/FAT32-partitions found during bootup.  
  
 More Info [MS KB156560](http://support.microsoft.com/kb/156560 "Free Space Required to Convert FAT to NTFS [Q156560]")  
 More Info [MS KB214579](http://support.microsoft.com/kb/214579 "How to Use Convert.exe to Convert a Partition to the NTFS File System (Win2k) [Q214579]")  
 More Info [MS KB295723](http://support.microsoft.com/kb/295723 "The Autoconvert Tool Does Not Convert a FAT to NTFS because of "insufficient memory" [Q295723]")  
 More Info [MS KB307881](http://support.microsoft.com/kb/307881 "HOW TO: Convert a FAT16 or FAT32 Volume to NTFS in Windows XP [Q307881]")  
 More Info [MS KB314097](http://support.microsoft.com/kb/314097 "How to Use Convert.exe to Convert a Partition to the NTFS File System (WinXP) [Q314097]")  