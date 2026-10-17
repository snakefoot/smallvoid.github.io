---
title: 'Configure I/O requests for SCSI devices'
date: '2004-03-06T12:53:12+01:00'
permalink: /article/winnt-scsi-request-limit.html
author: Snakefoot
excerpt: 'How to increase the allowed amount of concurrent I/O request for a disk controller.'
type: post
id: 34
categories:
    - windows-2000_performance
    - windows-2003_performance
    - windows-nt4_performance
    - windows-xp_performance
tags:
    - disk-performance
    - drivers
    - hard-disk-drive
    - scsi
---
There is a limit for how many concurrent SCSI Request Block (SRB) Windows can make to a SCSI device. The default limit is 16 requests, but if it is a highspeed SCSI device (RAID) then performance might be improved with a higher value:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\MINIPORT\_ADAPTER \\Parameters \\DeviceX\]  
>  NumberOfRequests = 64 (Default = 16, Max = 512)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+240314+Q240314" rel="nofollow" title="INFO: Restriction on the Number of Concurrent I/O Requests Setting [Q240314]">MS KB240314</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+329075+Q329075" rel="nofollow" title="Dmio Reports Event ID 30 with Status of 0xC000009A [Q329075]">MS KB329075</a>

 When a request is sent to the SCSI device it is done with a Scatter/Gather list, which specifies the physical memory blocks used for the transfer. The list is default limited to max 17 elements (1 element is the list itself), but it is not a problem if the miniport driver is capable of using large continuously memory buffers (&gt;4 KByte). Incase the miniport driver is limited to 4 KByte memory blocks, the I/O request will only be 64 KByte (4 KByte\*16), then increasing the limit of the Scatter/Gather list might help performance:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\MINIPORT\_ADAPTER \\Parameters \\DeviceX\]  
>  MaximumSGList = 65 (Default = 17, Max = 255)  
>   
>  More Info [MSDN - Registry Entries for SCSI Miniport Drivers](http://msdn2.microsoft.com/en-us/library/ms802344.aspx)

 Note MINIPORT\_ADAPTER is the name of the miniport driver, such as AIC78xx, and X (from DeviceX) is the bus number assigned at initialization.  
  
 Note be careful with increasing these values as they consume non paged memory (Page Table Entries).  
  
 Note if having performance problem then first make sure that write caching is enabled for the SCSI HDDs (Unless requiring secure write).  
  
 Note WinXP has a fault in its NTFS driver, that causes low performance with SCSI disks, which has been fixed in SP1.