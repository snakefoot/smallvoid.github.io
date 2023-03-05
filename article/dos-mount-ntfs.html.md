---
title: 'Mount NTFS partitions using DOS device driver'
date: '2000-01-01T14:22:04+01:00'
status: publish
permalink: /article/dos-mount-ntfs.html
author: Snakefoot
excerpt: 'Mounts NTFS partitions in DOS, so one can access the files.'
type: post
id: 77
category:
    - Utilities
tag:
    - bootdisk
    - drive-mount
    - ntfs
    - partition
post_format: []
tags:
    - 'ntfs,bootdisk,drive-mount,partition'
---
MS DOS doesn't recognize disk partitions formatted as NTFS, but one can load a device driver that enables one to access NTFS partitions from a DOS prompt.

- [NTFSDOS](http://www.sysinternals.com/Utilities/NtfsDos.html) by SysInternals.com ([Download Mirror](http://smallvoid.orgfree.com/?file=ntfsdos.zip "NTFSDOS Version V3.02R+")) makes it possible to mount NTFS partitions in DOS and access the files.
- [NTFS Reader](http://www.ntfs.com/products.htm) by Active@ is a file manager that allows one to browse NTFS partitions from DOS. It supports long filenames and NTFS compression.
- [NTFS4DOS](http://www.free-av.com/en/tools/11/avira_ntfs4dos_personal.html) by Avira allows both read and write access to NTFS partitions. More Info [Bootdisk.com](http://www.bootdisk.com/ntfs.htm)
 
 These utilities can be useful if the WinNT installation has gone fubar and you want some files recovered from the disk before reinstall using a [DOS bootdisk](/article/dos-bootdisk.html)