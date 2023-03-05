---
title: 'Create Windows 2000 bootable CD using CDRWIN'
date: '2003-02-28T05:21:14+01:00'
status: publish
permalink: /article/win2k-bootable-cd-cdrwin.html
author: Snakefoot
excerpt: 'Using CDRWIN to make a bootable install cd for Windows 2000.'
type: post
id: 481
category:
    - 'Install CD'
tag:
    - bootdisk
post_format: []
tags:
    - bootdisk
---
To merge the win2k install files with an extracted boot sector into an ISO using [Goldenhawk CDRWIN](http://www.goldenhawk.com/):

- Your Win2k install files should be placed in (Drive Letter):\\win2kcd\\
- Your [extracted boot sector](/article/win2k-install-cd-boot-sector.html) should be saved as (Drive Letter):\\win2kboot\\boot.bin

1. Start CDRWIN
2. Choose the "File Backup and Tools" option and choose "Build an ISO9660"
3. In "File Backup" click the "Directory" button and choose the (Drive Letter):\\win2kcd\\ directory and click the "Add" Button
4. In the big box uncheck "All" and check "Include Hidden Files", "Long FileNames(Joliet)", "Include System Files" and "Recurse SubDirectories"
5. For "Image File" click the "..."-button at the right and choose to place the iso image file somewhere you like
6. Check the box "Disable Version Numbers"
7. Click the "Advanced Options" button
8. At the "Volume Descriptor" tab 
  - Volume Label = (Label of your Win2k-cdrom)
  - Volume Set Name = (Label of your Win2k-cdrom) 
      - W2PFPP\_EN : If using MSDN Win2k Prof. US
      - W2SFPP\_EN : If using MSDN Win2k Srv. US.
      - W2AFPP\_EN : If using MSDN Win2k Adv. Srv. US
      - W2PIS\_EN : If using Standard Win2k Prof. US
      - W2SIS\_EN : If using Standard Win2k Srv. US.
      - W2AIS\_EN : If using Standard Win2k Adv. Srv. US
  - Publisher Name = MICROSOFT CORPORATION
  - Preparer Name = MICROSOFT CORPORATION, ONE MICROSOFT WAY, REDMOND WA 98052, (206) 882-8080
9. At the "Bootable Disc" tab 
  - Check the box "Make Bootable disc"
  - Media Emulation Type = Custom
  - Image File Name = (Drive Letter):\\win2kboot\\boot.bin (The boot.bin created above)
  - Developer Name = MICROSOFT CORPORATION
  - Load Segment = 07C0
  - Load Sector Count = 4
10. Click the "Ok" button and then "Start"
11. After that burn the Iso Image File with any CD-ROM burner program
 
 Credits [ntcompatible.com](http://www.ntcompatible.com/)  