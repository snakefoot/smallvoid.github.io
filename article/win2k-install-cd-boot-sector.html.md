---
title: 'Extract boot sector from Windows 2000 CD using CDRWIN'
date: '2003-02-28T04:47:55+01:00'
status: publish
permalink: /article/win2k-install-cd-boot-sector.html
author: Snakefoot
excerpt: 'When creating a bootable cd then one must provide a boot sector, which can be extracted from the original cd.'
type: post
id: 480
category:
    - 'Install CD'
tag:
    - boot-sector
    - slipstream
post_format: []
tags:
    - 'boot-sector,slipstream'
---
To extract the boot sector from the original Windows 2000 bootable cd with [Goldenhawk CDRWIN](http://www.goldenhawk.com/) :

1. Start CDRWIN and choose the "'Extract Disc/Tracks/Sectors"
2. Select Extract mode "Select Sectors"
3. Set image file to be (Drive Letter):\\win2kboot\\boot.bin
4. Set File Format to be Automatic
5. Set the sector selection to sector 20 (by setting start- and end-sector to 20)
6. Set Data Mode to "Mode1 (2048)" and press start
 
 Note if the above steps seems cumbersome, then one can just download [win2kboot.zip](http://smallvoid.orgfree.com/?file=win2kboot.zip) and extracting BOOT.BIN to a new folder (Drive Letter):\\win2kboot\\  
  
 More Info [Bart's Boot Image Extractor](http://www.nu2.nu/bbie/) a command line tool to extract the bootsector.  
 More Info [Bart's way to create bootable CD-Roms](http://www.nu2.nu/bootcd/)  