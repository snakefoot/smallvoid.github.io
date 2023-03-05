---
title: 'BootPart to add several boot partitions to boot.ini'
date: '2001-09-04T15:13:25+02:00'
status: publish
permalink: /article/winnt-bootpart.html
author: Snakefoot
excerpt: 'Bootpart makes it easy to create the perfect multi-boot setup using the Windows NT boot manager.'
type: post
id: 496
category:
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag:
    - boot-manager
    - dual-boot
    - partition
post_format: []
tags:
    - 'boot-manager,partition,dual-boot'
---
This is a really cool utility which is able to take the image of the boot sector of any partition and save it in a file. It also can restore the bootsector of the WinNT partition if it has been overwritten.  
  
 This can used for creating a [multi-boot](/article/winnt-dual-boot.html) configuration where each operating system is placed on their own primary boot partition. Ex. one can use Win2k and Win98 together without any special [boot manager](/article/boot-manager.html) like System Commander. This is done by installing Win2k(NTFS) and Win98(FAT32) on their own separate primary partition. Then run this utility when in Win2k, and it can extract the bootsect.dos image of the Win98 partition and insert Win98 in the Win2k boot manager.  
  
 Note with WinXP the [recovery console](/article/winnt-recovery-console.html) has been extended with the command bootcfg which acts just like this util.