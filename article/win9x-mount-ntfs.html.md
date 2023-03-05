---
title: 'Mount NTFS partitions inside Windows 9x'
date: '2000-01-01T22:49:46+01:00'
status: publish
permalink: /article/win9x-mount-ntfs.html
author: Snakefoot
excerpt: 'NTFS device driver for accessing NTFS partitions inside Windows 9x.'
type: post
id: 222
category:
    - Utilities
    - Utilities
    - Utilities
tag:
    - drive-mount
    - ntfs
    - partition
post_format: []
tags:
    - 'ntfs,partition,drive-mount'
---
Microsoft Windows 95 / 98 / Me doesn't have native support for NTFS partitions, but there exists different file system drivers, which allows one to mount an NTFS partitions and access it like a normal FAT16 / FAT32 partition.

- [NTFS for Windows 98 (NTFS98)](http://www.sysinternals.com/Utilities/NtfsWindows98.html) by SysInternals.com ([Download Mirror of Ntfs98ro.exe](http://smallvoid.orgfree.com/?file=ntfs98ro.exe.zip "NTFS for Windows 98 Version 2.0")) works with Win95, Win98 and WinMe, but limited to read-only mode.
- [DiskInternals NTFS Reader](http://www.diskinternals.com/products/ntfs-reader/) works with Windows 95, 98 and Me, but limited to read-only mode.
 
 Related [NTFSDOS](/article/dos-mount-ntfs.html)