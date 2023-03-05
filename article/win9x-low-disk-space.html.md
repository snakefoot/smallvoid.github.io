---
title: 'Configure low disk space warning in Windows 98/Me'
date: '2003-06-21T01:51:38+02:00'
status: publish
permalink: /article/win9x-low-disk-space.html
author: Snakefoot
excerpt: 'Description of the low disk space warning and how to disable it.'
type: post
id: 123
category:
    - Tips
    - Tips
tag:
    - hard-disk-drive
post_format: []
tags:
    - hard-disk-drive
---
By default when a partition is near being full the following message pops up:

> Hard Disk is Full  
>   
>  You have run out of disk space on drive C. To free space on this drive by deleting old or unnecessary files, click Disk Cleanup

 This can be rather annoying especially when copying files between almost full partitions. To disable this popup warning for a drive:
1. Open **My Computer**
2. Right click the wanted drive and choose **Properties**
3. On the **General** fan, press the **Disk Cleanup...** button
4. Select the **Settings** fan
5. Uncheck **If this drive runs low on disk space, automatically run Disk Cleanup**
6. Press **Ok**
7. A popup comes up about deleting temporary files, press **Ok**
 
 The above actions are reflected in this DWORD registry value:
 
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\FileSystem\]  
 >  DisableLowDiskSpaceBroadcast = 12 (Disable checking on C: and D:)

 <table border="1"><tr><th>Bit</th><th>Value(Dec)</th><th>Value(Hex)</th><th>Letter</th></tr><tr><td>1</td><td>1</td><td>0x00000001</td><td>A:</td></tr><tr><td>2</td><td>2</td><td>0x00000002</td><td>B:</td></tr><tr><td>3</td><td>4</td><td>0x00000004</td><td>C:</td></tr><tr><td>4</td><td>8</td><td>0x00000008</td><td>D:</td></tr><tr><td>5</td><td>16</td><td>0x00000010</td><td>E:</td></tr><tr><td>etc.</td><td>etc.</td><td>etc.</td><td>etc.</td></tr></table>

  
 More Info [MS KB188074](http://support.microsoft.com/kb/188074 "Low Disk Space Notification Received When Drive Is Full [Q188074]")  
  
 Related [Configure different cleanup profiles for different drives](/article/cleanup-profiles.html)  
  
 Credits [www.mdgx.com](http://www.mdgx.com/)