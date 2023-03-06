---
title: 'Description of the hard disk cache'
date: '2007-04-19T19:43:09+02:00'
status: publish
permalink: /article/hard-disk-cache.html
author: Snakefoot
excerpt: 'The hard disk performance is very dependent on the configuration of the disk cache.'
type: post
id: 340
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - disk-performance
    - file-cache
    - hard-disk-drive
post_format: []
tags:
    - 'hard-disk-drive,file-cache,disk-performance'
---
The hard disk is extremely slow compared to physical memory (RAM), but provides lots of storage capacity. Disk caching can be used to speed up the harddisk performance. The disk cache uses RAM to provide quick access to frequently accessed data.  
  
 There are different levels of disk caching:

- Hard disk Cache - Cache is located on the hard disk device and works only with sectors. It allows continuous reading from the disk even if the transfer-bus is busy.
- Disk controller Cache - Cache is located on the controller card and works only with sectors. It allows reading from disk without using the transfer-bus to contact the hard disk.
- Operating System Cache - Using RAM as hard disk cache and works on a file level. It allows file access without using the system-bus to contact the disk controller. 
  - [Win9x/WinMe : System File Cache](/article/win9x-disk-cache.html)
  - [WinNT+ : System File Cache](/article/winnt-system-cache.html)
- Vista [Readyboost](/article/winnt-services-emdmgmt.html) - Cache is placed on high speed USB flash drives, which allows faster seek times and higher constant transfer rate than the HDD. Can deliver a very large and fast hard disk cache, though still slower than RAM.
 
 There are usually two types of disk caching:
- **Read Cache** - Allows the hard disk to read data ahead in the background, so the application doesn't have to block while waiting for the data to be read, but gets the data delivered from the cache instead.
- **Write Cache** - Allows the hard disk to lazy write data in the background, so the application doesn't have to block while waiting for the data to be written, but enters the cache where it is later written to the hard disk.

##### How does write caching work?

 Disk caching greatly improves disk performance, but there is a drawback to Write caching, as anything written to the cache, which haven't been flushed to the disk will be lost when the power is lost. Most applications are aware of this behavior, and the operating system provides the ability to perform a direct write or flushed write. Write flushing means that the application will wait for the data to be written to disk before continuing, instead of just writing to the cache which completes right away.  
  
 Windows 3.11 had a flaw in its flush operation, so it actually just performed a lazy write to the cache when an application performed a flushed write. Several applications was created which was littered with flushed writes, because it performed so well. These applications performed miserable when used on Windows 95, which didn't have this flaw when performing flushed write, and naturally was much slower than just writing to the cache. One could activate the old buggy behavior by with the option to "Disable Synchronous Buffer Commits", which was hidden away in the troubleshooting section.  
  
 Later as server environments have become more and more stable with duplicate power supplies and UPS equipment, then the idea of actually ignoring the flush request has become a wish for those where high disk performance is critical. The Windows operating system can convert the following requests to normal I/O requests so the cache buffers are not flushed:
- **Write Through** - Performs a write to disk without using the cache. Activated by calling the Windows API WriteFile() with FILE\_FLAG\_WRITE\_THROUGH. Sends a Forced Unit Access (FUA) command to the storage device.
- **Flush Buffers** - Tells the disk to flush everything it has in cache. Activated by calling FlushFileBuffers(). Sends a Synchronize Cache (SCSI) or Flush Cache (IDE/ATAPI) command to the storage device.

##### When to enable write caching?

 The promise of increased performance is always nice, but when the price is the risk of dataloss, then one should be very carefull with changing the behavior of these disk requests.  
  
 It is not recommended to enable write caching on standard desktop/laptop machine, which can shutdown unexpectedly or freeze/crash because of a software/hardware error.  
  
 It is also not recommended to enable write caching when running a Database Management System (DBMS), as these requests are used to create stable commit checkpoints before beginning on a new transaction.  
  
 But if having a seperate harddisk for the [pagefile](/article/windows-page-file.html) or other temporary files, then there can be a performance boost with no cost.
 
##### How to configure write caching?

- Windows 2000 SP3 / XP SP2 - Requires the utility **Dskcache.exe** to enable **Power Protected** write cache. More Info [MS KB811392](http://support.microsoft.com/kb/811392 "Obtain the Dskcache.exe Tool to Configure the "Power Protected" Write Cache Option [Q811392]"), [MS KB332023](http://support.microsoft.com/kb/332023 "Slow Disk Performance When Write Caching Is Enabled [Q332023]")
- Windows 2003 / Vista - The option with the misleading name "Enable Advanced Performance", which can be found on the "Policies"-tab for each hard disk device in the "Device Manager" (Have to activate "Optimize for performance" and "Enable write caching on the disk").
- Windows 7 - The option is called "Turn off Windows write-cache buffer flushing on the device.", which can be found on the "Policies"-tab for each hard disk device in the "Device Manager" (Have to activate "Enable write caching on the device")
 
 More Info [MS KB324446](http://support.microsoft.com/kb/324446 "Terminal Server and connected Terminal Services clients pause when a Terminal Services client logs on or logs off [Q324446]")  
 More Info [Microsoft - Windows Confidential: The Power of Bugs](http://www.microsoft.com/technet/technetmag/issues/2007/04/WindowsConfidential/default.aspx "Raymond Chen April 2007 issue of TechNet Magazine")  
  
 Related [Configure IDE ATA hard disk for best performance](/article/troubleshoot-hdd-dma.html)