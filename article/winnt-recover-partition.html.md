---
title: 'Recover deleted NTFS/FAT32 partition'
date: '2006-01-10T01:53:26+01:00'
status: publish
permalink: /article/winnt-recover-partition.html
author: Snakefoot
excerpt: 'When deleting a partition then only the boot sector is modified, so by restoring the boot sector, then one will restore the partition.'
type: post
id: 473
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - boot-sector
    - fat32
    - file-recovery
    - file-system
    - hard-disk-drive
    - ntfs
    - partition
    - partition-recovery
    - system-recovery
post_format: []
tags:
    - 'boot-sector,partition,hard-disk-drive,partition-recovery,file-recovery,system-recovery'
---
When a dynamic volume is deleted, the OS clears the boot sector of the partition and removes the volume entry from the Disk Management MMC, but leaves the rest of the data on the partition untouched. Both NTFS and FAT32 stores a backup of the boot sector and if restored, then it will be possible to recover a deleted partition.  
  
 To recover a dynamic NTFS volume:

- Start the Disk Management snapin (Go to Start, Programs, Administrative Tools, Computer Management and select Storage)
- Recreate the original volume by right-clicking the unpartitioned space and selecting New Partition. Specify the exact size of the original volume, but do not perform a format of the volume.
- Use **Dskprobe.exe** to recover the backup boot sector (You might need **Dmdiag.exe** to find the backup boot sector). More Info [Recovering NTFS Boot Sector on NTFS Partitions (MS KB153973)](http://support.microsoft.com/kb/153973 "Recovering NTFS Boot Sector on NTFS Partitions [Q153973]")
- After restoring the NTFS boot sector quit Dskprobe.exe
- In the Disk Management snapin go to the Action-menu and click Rescan Disks to mount the volume for immediate use.
 
 To recover a FAT32 volume:
- Start the Disk Management snapin (Go to Start, Programs, Administrative Tools, Computer Management and select Storage)
- Recreate the original volume by right-clicking the unpartitioned space and selecting New Partition. Specify the exact size of the original volume, but do not perform a format of the volume.
- Use **Dskprobe.exe** to recover the backup boot sector from the sector-6 of the logical volume and write it to sector-0 of the logical volume. More Info [Chkdsk Does Not Use Backup Boot Sector to Fix Corrupted FAT32 Boot Sector (MS KB247575)](http://support.microsoft.com/kb/247575 "Chkdsk Does Not Use Backup Boot Sector to Fix Corrupted FAT32 Boot Sector [Q247575]")
- After restoring the FAT32 boot sector quit Dskprobe.exe
- In the Disk Management snapin go to the Action-menu and click Rescan Disks to mount the volume for immediate use.
 
 More Info [MS KB246146](http://support.microsoft.com/kb/246146 "Dskprobe.exe May Damage FAT32 Boot Sector [Q246146]")  
 More Info [MS Technet](http://www.microsoft.com/technet/prodtechnol/Windows2000Pro/reskit/part7/proch32.mspx "Disk Concepts and Troubleshooting")  
  
 Related [TestDisk](/article/windows-undelete.html) (Tool for recovery deleted partitions)  
  
 Credits [NtFaq.com](http://www.windowsitpro.com/Articles/Index.cfm?ArticleID=25375)