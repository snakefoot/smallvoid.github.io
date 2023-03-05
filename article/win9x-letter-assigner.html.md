---
title: 'Letter Assigner'
date: '2003-05-25T00:06:12+02:00'
status: publish
permalink: /article/win9x-letter-assigner.html
author: Snakefoot
excerpt: 'Utility that allows one to change drive-letter assignments for hard disk partitions.'
type: post
id: 114
category:
    - Utilities
    - Utilities
    - Utilities
tag:
    - drive-letter
    - partition
post_format: []
tags:
    - 'drive-letter,partition'
---
[Letter Assigner](http://www.v72735.f2s.com/LetAssig/ "Vadin Burtyansky") (Download [mirror of LetAssig.zip](http://smallvoid.orgfree.com/?file=letassig.zip "Letter Assigner v1.2.0 by Vadim Burtyansky")) makes it possible to assign specific drive letter to any partition.  
  
 Letter Assigner remebers drives by their serial numbers or by the labels, which provides protection against letter changes after repartitioning or connecting new drives. It also prevents non-bootable situations that may occur when Windows® directory is located on a drive other than C, and the drive changes its letter. ( It contains special mechanism for this purpose, including automatic correction of the files "msdos.sys", "winboot.ini", "config.sys" ).
 
##### Screenshots

 ![](/tweak/win9x/pictures/letassign_mainwindow.gif)  
 In the upper part of the window you see the letter bar ( toolbar with the letters A,B,...,Z ). It shows free letters that are not assigned to any drive and that are available for assignment. The used letters are grayed out. You can use several methods to assign letters:
- Drag a letter from the letter bar and drop it on a drive.
- Drag a letter from one drive and drop it on another.
- Select a drive from the list and click an active button on the letter bar.
- Select a drive from the list and press a key from 'A' to 'Z' on the keyboard.
- Click the "Delete" button or choose "Edit/Clear" menu item to clear the letter for the selected drive.
- Use "Edit / Clear All" menu item or press Ctrl+A to clear all the letters and start from the blank sheet.
- Use "Edit / Restore Original" menu item or press Ctrl+Z to restore the letter set that is currently used by the system. In other words, this command copies the "Old" column to the "New" column.
 
 The drive list looks like "My computer" in the details view mode, but provides additional information about the drives:
- file system ( FAT12, FAT16 or FAT32 );
- serial number;
- information about compression, if your system has compressed drives : whether the drive is a host or a compressed drive, for a compressed drive - the host letter and the unit number, for a host drive - all its compressed drives. If the host and the compressed drive are swapped, it is also indicated.
- if some drives are hidden, the additional column "Hid" appears, that marks hidden drives by "H".
 
 By double-clicking on a drive you can invoke its device properties:  
![](/tweak/win9x/pictures/letassign_deviceprop.gif)  
 Particularly, you can use the option "Maximum number of letters" to reserve desirable number of letters for protected mode only drives ( it is disabled for the drives visible in MS-DOS® mode ). It is useful when you need to limit the number of letters for a device or to add new partitions to an existing disk. 