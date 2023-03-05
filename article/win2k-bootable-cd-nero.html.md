---
title: 'Create Windows 2000 bootable CD using NERO v5.5.9.0'
date: '2003-02-28T05:38:54+01:00'
status: publish
permalink: /article/win2k-bootable-cd-nero.html
author: Snakefoot
excerpt: 'Using Nero Burning Rom to make a bootable install cd for Windows 2000.'
type: post
id: 482
category:
    - 'Install CD'
tag:
    - bootdisk
post_format: []
tags:
    - bootdisk
---
Note previous Nero versions requires a registry key to be setup to work properly.

1. Start Nero
2. Close all windows inside Nero
3. In the menu choose "Recorder" : 
  - Select "Image Record" if you want to save to an ISO file
  - Select your CD-Writer if you want to burn directly to CD
4. In the menu choose "File" and select "New..."
5. In the "New Compilation" Window select "CD-ROM (Boot)"
6. Go to tab "Boot" 
  - Pick "Image File" and browse to your [extracted boot-sector](/article/win2k-install-cd-boot-sector.html)
  - Tick "Enable expert settings"
  - "Kind of emulation" = "No Emulation"
  - "Number of loaded sectors" = 4 (Important)
7. Go to tab "ISO" 
  - Pick "ISO Level 2"
  - Pick "Mode 1" format
  - Pick "ISO 9660" Character Set
  - Check "Joliet"
  - Check "Allow pathdepth of more than 8 directories"
  - Check "Allow more than 255 characters in path"
  - Check "Do not add the ';1' ISO file version extension" (Important)
8. Go to tab "Label" 
  - "Volume Label" and "Volume Set" = 
      - W2PFPP\_EN : If using MSDN Win2k Prof. US
      - W2SFPP\_EN : If using MSDN Win2k Srv. US.
      - W2AFPP\_EN : If using MSDN Win2k Adv. Srv. US
      - W2PIS\_EN : If using Standard Win2k Prof. US
      - W2SIS\_EN : If using Standard Win2k Srv. US.
      - W2AIS\_EN : If using Standard Win2k Adv. Srv. US
  - "Publisher" = MICROSOFT CORPORATION
  - "Data Preparer" = MICROSOFT CORPORATION, ONE MICROSOFT WAY, REDMOND WA 98052, (206) 882-8080
9. Press "New" Button
10. Drag the Win2k install files into the ISO window
11. Right the volume label in the ISO Window and select properties, and check if everything is set correctly
12. Burn the CD
 
 Credits [Bink : Making a Bootable Windows 2000 CD with Service Pack Integrated](http://www.bink.nu/bootcd/)