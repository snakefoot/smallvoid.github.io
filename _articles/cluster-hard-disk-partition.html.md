---
title: 'Configure the cluster size of the hard disk partition'
date: '2000-01-01T00:08:31+01:00'
permalink: /article/cluster-hard-disk-partition.html
author: Snakefoot
excerpt: 'How to change the cluster size of a partition with description of the different filesystems and their limitations.'
type: post
id: 131
categories:
    - windows-2000_performance
    - windows-2003_performance
    - windows-95_performance
    - windows-98_performance
    - windows-me_performance
    - windows-nt4_performance
    - windows-xp_performance
tags:
    - allocation-unit
    - cluster-size
    - disk-performance
    - exFAT
    - fat16
    - fat32
    - file-system
    - hard-disk-drive
    - ntfs
    - partition
---
The physical HDD is divided into sectors, which is the smallest unit of storage possible. The sector-size is defined during the low-level format performed by the HDD-manufacture (Standard 512 Bytes).  
 When formatting a HDD-partition it is divided into clusters with a certain cluster-size. A cluster is a group of sectors and can can only be occupied by one file, so if having a 10 KByte file and a 4 KByte cluster-size, the file would occupy 3 clusters and 12 KByte space. This would create a so called "slack" of 2 KByte.  
  
 There is the following relation between Cluster Count, Cluster Size and Partition Size:

> Cluster Count \* Cluster Size = Partition Size

 Note the different filesystems(FAT, FAT32, NTFS, etc.) can impose a Max Cluster Count and Max Cluster Size.  
  
<table border="1">
<tr><td> </td> <th>FAT16</th> <th>FAT32</th> <th>NTFS</th> <th>exFAT</th></tr>
<tr><td>Max Cluster Size</td> <td>32K (64K WinNT)</td> <td>32K</td> <td>64K (4K [Compression](/article/winnt-ntfs-compress.html))</td> <td>32 MByte</td></tr>
<tr><td>Max Cluster Count</td> <td>65526</td> <td>268,435,445 (4,177,920 16Bit)</td> <td>4,294,967,296</td> <td>?</td></tr><tr><td>Max Partition Size</td> <td>2GB (4GB WinNT)</td><td>8TB (Actual 2TB, 127GB 16Bit)</td> <td>64 TB (Basic - 2TB)</td> <td>64 ZB (Best 512 TB)</td></tr>
<tr><td>Min Partition Size</td> <td>360 KByte (FAT12)</td><td>[512 MByte](/article/fdisk-small-fat32.html)</td> <td>10 MBytes</td> <td>?</td></tr><tr><td>Max File Size</td> <td>2GB (4GB WinNT)</td><td>4GB</td> <td>16EB (Basic - 2TB)</td> <td>64 ZB (Best 512 TB)</td></tr>
<tr><td>Max File Name Length</td><td>8.3 (255 VFAT)</td><td>255</td> <td>255</td> <td>?</td></tr><tr><td>Max Path Name Length</td><td>260</td> <td>260</td> <td>32767</td> <td>?</td></tr><tr><td>Max Files in Partition</td><td>65536 (32768 VFAT)</td><td>4,194,304</td> <td>4,294,967,295</td> <td>?</td></tr>
<tr><td>Max Files in Directory</td><td>65536 (32768 VFAT)</td><td>65536</td> <td>4,294,967,295</td> <td>?</td></tr><tr><td>Max Files in Root</td> <td>512 (256 VFAT)</td> <td>65536</td> <td>4,294,967,295</td> <td>?</td></tr><tr><td>Performance</td> <td>High (Small Volume)</td><td>High</td> <td>High (Large Volume)</td> <td>High (Flash Drives)</td></tr>
<tr><td>File Fragmentation</td><td>High (First free location)</td><td>High (First free location)</td><td>Low (Free Space Bitmap)</td><td>Low (Free Space Bitmap)</td></tr><tr><td>Compression</td> <td>3rd Party</td> <td>3rd Party</td> <td>Native</td> <td>?</td></tr><tr><td>Access Control</td> <td>No</td> <td>No</td> <td>Native</td> <td>Native</td></tr>
<tr><td>Encryption</td> <td>3rd Party</td> <td>3rd Party</td> <td>Native</td> <td>?</td></tr><tr><td>Resizable</td> <td>3rd Party</td> <td>3rd Party</td> <td>Native</td> <td>?</td></tr><tr><td>Software RAID</td> <td>No</td> <td>No</td> <td>Native (Basic - No)</td> <td>?</td></tr>
<tr><td>Recoverability</td> <td>Little</td> <td>Better (Several FATs)</td> <td>Best (Logged)</td> <td>Best (Logged)</td></tr><tr><td>Cross Platform</td> <td>Native</td> <td>3rd Party</td> <td>3rd Party</td> <td>3rd Party</td></tr>
</table>

 Note the abilities of the NTFS volumes are dependent on whether they are placed on basic or dynamic disks. More Info <a href="https://www.bing.com/search?q=KB+314343+Q314343" rel="nofollow" title="Basic Storage Versus Dynamic Storage in Windows XP [Q314343]">MS KB314343</a>.  
 When a basic disk is converted to a dynamic disk, then any volumes that existed on the basic disk will still only be able to extend into unformatted areas next to them <a href="https://www.bing.com/search?q=KB+325590+Q325590" title="How to use Diskpart.exe to extend a data volume in Windows Server 2003, in Windows XP, and in Windows 2000 [Q325590]" rel="nofollow">using diskpart</a>. More Info <a href="https://www.bing.com/search?q=KB+225551+Q225551" rel="nofollow" title="Restrictions on Extending or Spanning Simple Volumes on Dynamic Disks [Q225551]">MS KB225551</a>.  
  
 Note the 16 Bit limit in FAT32 is only important if planning to use 16 bit disk tools such as DOS scandisk, which cannot allocate enough memory to handle a file allocation table (FAT) larger than 16 MByte.  
 There is also a limit in Win2k/XP not to create and format FAT32 partitions beyond 32 GByte to encourage usage of NTFS.  
  
 Note the VFAT (Virtual-FAT) is an extension of the FAT16 to support long filenames, but it can halve the amount of max files/directories because it uses an extra entry for storage of each long filename (If the filename is beyond the 8.3 mask). This can be important if having many files/directories with long filenames in the root like on a floppy disk.  
  
 To check the cluster size of an already formatted partition (Where X is the partition letter):

> Chkdsk X:

 To format a partition with specific cluster size:
 - In Win95 OSR2 and beyond it is possible to specify the cluster-size when formatting (Before the choice was made for you). With the parameter /Z one can specify a multiplier of sector size (Standard 512 bytes), so if using 8, then one will get a cluster size of 4096 bytes:

> Format X: /Z:8

- In WinNT the /FS parameter specifies filesystem (NTFS/FAT16/FAT32) and /A specifies cluster size (aka Allocation-unit):

> Format X: /FS:NTFS /A:4096
 
 Usually an cluster-size of 4 KByte seems to be a good choice as it matches the page size used in memory, but there is no standard optimal cluster-size which can be applied for every disk critical application in every environment. It depends on the HDD, Controller (If RAID also the selected Stripe-Size), Filesystem (FAT,NTFS, etc.) and the application itself. To find the optimal cluster-size:
1. Backup the partition.
2. Format the partition with the new cluster-size.
3. Restore the backup.
4. Benchmark the partition using the disk critical application.
5. Repeat until optimal cluster-size is found.
 
 Considerations about choosing cluster-size:
- A small cluster size (4 KByte) is good when the partition will contain lots of small files, as it will minimize "slack".
- A large cluster size (16-32 KByte) is good when the partition will contain large files (Fileserver, video-editing, etc.), as it will lower the possibility of file fragmentation, and also makes the File Table (Maps files to what clusters they uses) smaller.
- Windows 2000 cannot [defrag](/article/winnt-defrag-tools.html) a partition if the cluster size is larger than 4 KByte.
 
 More Info <a href="https://www.bing.com/search?q=KB+39927+Q39927" rel="nofollow" title="MS-DOS: Directory and Subdirectory Limitations [Q39927]">MS KB39927</a>  
 More Info <a href="https://www.bing.com/search?q=KB+93496+Q93496" rel="nofollow" title="Windows NT File Size and Partition Size Limits [Q93496]">MS KB93496</a>  
 More Info <a href="https://www.bing.com/search?q=KB+100108+Q100108" rel="nofollow" title="Overview of FAT, HPFS, and NTFS File Systems [Q100108]">MS KB100108</a>  
 More Info <a href="https://www.bing.com/search?q=KB+118335+Q118335" rel="nofollow" title="Maximum Partition Size Using FAT16 File System [Q118335]">MS KB118335</a>  
 More Info <a href="https://www.bing.com/search?q=KB+120138+Q120138" rel="nofollow" title="Errors Creating Files or Folders in the Root Directory [Q120138]">MS KB120138</a>  
 More Info <a href="https://www.bing.com/search?q=KB+140365+Q140365" rel="nofollow" title="Default Cluster Size for FAT and NTFS [Q140365]">MS KB140365</a>  
 More Info <a href="https://www.bing.com/search?q=KB+154997+Q154997" rel="nofollow" title="Description of the FAT32 File System [Q154997]">MS KB154997</a>  
 More Info <a href="https://www.bing.com/search?q=KB+184006+Q184006" rel="nofollow" title="Limitations of FAT32 File System [Q184006]">MS KB184006</a>  
 More Info <a href="https://www.bing.com/search?q=KB+224526+Q224526" rel="nofollow" title="Windows NT 4.0 Supports Maximum of 7.8-GB System Partition [Q224526]">MS KB224526</a>  
 More Info <a href="https://www.bing.com/search?q=KB+240672+Q240672" rel="nofollow" title="Setup Does Not Check for INT-13 Extensions Before Creating System Partition [Q240672]">MS KB240672</a>  
 More Info <a href="https://www.bing.com/search?q=KB+310525+Q310525" rel="nofollow" title="Description of the FAT32 File System in Windows XP [Q310525]">MS KB310525</a>  
 More Info <a href="https://www.bing.com/search?q=KB+310561+Q310561" rel="nofollow" title="Maximum Partition Size Using the FAT16 File System in Windows XP [Q310561]">MS KB310561</a>  
 More Info <a href="https://www.bing.com/search?q=KB+314463+Q314463" rel="nofollow" title="Limitations of the FAT32 File System in Windows XP [Q314463]">MS KB314463</a>  
 More Info <a href="https://www.bing.com/search?q=KB+314878+Q314878" rel="nofollow" title="The Default Cluster Size for the NTFS and FAT File Systems [Q314878]">MS KB314878</a>  
  
 Credits [pureperformance.com](http://www.pureperformance.com/)