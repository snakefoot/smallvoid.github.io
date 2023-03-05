---
title: 'Configure the Master File Table for the NTFS partitions'
date: '2000-01-01T00:35:49+01:00'
status: publish
permalink: /article/winnt-ntfs-mft.html
author: Snakefoot
excerpt: 'The Master File Table is the index for all files and directories placed on a ntfs partition and critical for ntfs performance.'
type: post
id: 292
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - disk-performance
    - file-system
    - master-file-table
    - ntfs
post_format: []
tags:
    - 'file-system,ntfs,master-file-table,disk-performance'
---
Each NTFS partition has a Master File Table(MFT), which is used when looking up the location of files and empty space to place new files. The MFT is a file itself and it shrink and grows in size as the amount of files on the disk changes. Though when a file is deleted then the MFT file doesn't shrink, but the record that points to the deleted file is marked as free (ready for reuse), so the MFT file doesn't shrink unless special defragmentation tools are used.  
  
 The MFT file has two logical parts:

1. Metadata that describes the location of the files used to maintain the NTFS filesystem and their location (16 records of 1 KByte each) 
  - $MFT (The MFT itself and known by the boot sector)
  - $MFTmirr (Mirror of the MFT metadata and known by the boot sector)
  - [$LogFile](/article/winnt-ntfs-recovery-log.html) (Journaling support file)
  - $Volume (Information for the volume, such as the volume label, file system version, etc.)
  - $. (Root directory)
  - $Bitmap (Volume free space bitmap to find unused space)
  - $Boot (Boot sector)
  - $badclus (Bad Cluster File - Specifies all the bad clusters on the volume to avoid reuse)
  - $Quota (Users rights on disk space usage)
  - $Upcase (Maps accordance between upper and lower case letters for file names)
2. Collection of records where each describes the location of a file or directory on the partition. Each record uses 1 KByte and is also called a File Record Segment (FRS).
 
 It is important that the MFT-File doesn't become fragmented as lookups in the MFT will become slow, and affect overall disk performance:
- Always make sure that all NTFS drives has a minimum of 10% free space.
- Check that the MFT is not larger than the space reserved for it.
- Make sure that the [cluster size](/article/cluster-hard-disk-partition.html) of the partition is is 1024 bytes or more (4096 Bytes is preferred), as it supports the size of the FRS and causes less fragmentation. This can be an issue if having [converted from FAT16/FAT32 to NTFS](/article/winnt-convert-ntfs.html).
 
 To see the current size of the MFT file on a NTFS drive:
- **WinNT4**: Run this command:
 > dir /a $mft
- **Win2k+**: Start the Disk Defragmenter and analyze the disk and View Report.
 
 To specify how much of an NTFS volume should be reserved for the MFT, one can change this DWORD registry key (WinNT4 SP4+):  
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\FileSystem\]  
>  NtfsMftZoneReservation=2 (1=12,5%, 2=25%, 3=37,5%, 4=50%, Default=1)  
>   
>  Note it is only important to change this parameter if the MFT-File is becoming larger than the already reserved space (Mainly if having lots of small files on a small partition&lt;4 GB).  
>   
>  Note this parameter affects all NTFS volumes in the system.  
>   
>  Note it is recommended when changing this parameter to reformat the NTFS partitions, to make the change completely effective.  
>   
>  Note the space reserved for the MFT will be used for normal files if no free space is found else where on the drive.  
>   
>  More Info [MS KB174619](http://support.microsoft.com/kb/174619 "How NTFS Reserves Space for its Master File Table (MFT) [Q174619]")

 Note the utility fsutil can also be used to change this value:
> fsutil behavior set mftzone 1  
>   
>  The following values can be used: 1 = 12.5 %(default), 2 = 25%, 3 = 37.5%, 4 = 50%

 More Info [MS KB227350](http://support.microsoft.com/kb/227350 "Files Excluded by the Disk Defragmenter Tool [Q227350]")  
 More Info [MS KB303079](http://support.microsoft.com/kb/303079 "How to Locate and Correct Disk Space Problems on NTFS Volumes [Q303079]")  
 More Info [MS KB315688](http://support.microsoft.com/kb/315688 "How to Locate and Correct Disk Space Problems on NTFS Volumes in Windows XP [Q315688]")  
 More Info [MS KB320397](http://support.microsoft.com/kb/320397 "You receive an "NTLDR is missing" error message when you start your computer [Q320397]")  
  
 Credits [littleharbor.com](http://www.littleharbor.com/ntfs-details.htm)