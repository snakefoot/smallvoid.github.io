---
title: 'Create Win2k bootable CD using Adaptec CD Creator'
date: '2003-02-28T05:43:37+01:00'
status: publish
permalink: /article/win2k-bootable-cd-adaptec.html
author: Snakefoot
excerpt: 'Using Adaptec Easy CD Creator 5.02d to make a bootable install cd for Windows 2000.'
type: post
id: 483
category:
    - 'Install CD'
tag:
    - bootdisk
post_format: []
tags:
    - bootdisk
---
1. Start Easy CD Creator 5.02d Project Selector
2. Select "Make A Data CD"
3. Select "Data CD Project"
4. EZ CD Creator will start
5. In the menu choose "File", and select "New CD Project", Bootable CD
6. "Bootable CD Type" = "No Emulation"
7. "Sector Count" = 4
8. Choose "Browse" and locate the extracted boot sector file and press OK
9. In the lower left-hand screen right-click on the CD Icon and choose properties
10. Go to tab "General" 
  - "Volume Label" = 
      - W2PFPP\_EN : If using MSDN Win2k Prof. US
      - W2SFPP\_EN : If using MSDN Win2k Srv. US.
      - W2AFPP\_EN : If using MSDN Win2k Adv. Srv. US
      - W2PIS\_EN : If using Standard Win2k Prof. US
      - W2SIS\_EN : If using Standard Win2k Srv. US.
      - W2AIS\_EN : If using Standard Win2k Adv. Srv. US
  - "File System" = ISO9660
  - "Physical format of CD" = Mode 1: CDROM
11. Go to tab "File System" 
  - Publisher Name = MICROSOFT CORPORATION
  - Prepared By = MICROSOFT CORPORATION
  - Copyright = MICROSOFT CORPORATION
  - Select "Use original file date"
  - Select "Any MS-DOS 8.3 character file names"
12. Go to tab "File Types" 
  - Select "Add all Files"
  - Uncheck "Do not add Hidden files"
  - Uncheck "Do not add System files"
13. Press "Ok" button
14. In the Upper screen, located the folder containing the Win2k install files
15. Drag all the Win2k install files to the lower left-hand side of the screen
16. You can save the CD Image : 
  - In the menu select "File" and choose "Create CD Hard Disk Image..."
  - Type in a name for the image and save it as either .CIF or .ISO format
17. You can burn the CD image : 
  - In the menu select "File" and choose "Record CD"
 
 Credits [Bink : How to make your XP bootable](http://winxp.bink.nu/bootcd/default.htm)  