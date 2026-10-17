---
title: 'Configure Autorun for the CD-ROM drives'
date: '2001-01-01T23:47:13+01:00'
permalink: /article/winnt-autorun.html
author: Snakefoot
excerpt: 'Configure whether to automatically launch application when inserting a CD or DVD disk.'
type: post
id: 112
categories:
    - windows-2003_tips
    - windows-nt4_tips
    - windows-xp_tips
    - windows-2000_tips
tags:
    - autoplay
    - autorun
    - cdrom-drive
    - dvd-drive
---
It is possible to Disable/Enable the Autorun for all the CDROM drives with this DWORD registry value:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\CDRom\]  
>  Autorun=0

 Note to turn off autorun for Audio CDs alone:
1. Double click **My Computer**
2. In the menu select **Tools** and then **Folder Options**
3. Select the tab **File Types**
4. Select the registered file type **AudioCD** press the **Advanced** button
5. Without selecting any action press **Set Default** so no action is performed when an audio cd is inserted (If wanting to reenable the AutoPlay just select the action **Play** and press **Set Default**)
 
 Note in WinXP it is possible to configure AutoPlay by selecting properties for the CD-ROM/DVD drive. It is controlled by the [Shell Hardware Detection](/article/winnt-services-shellhwdetection.html) service.  
  
 Related [Configure autorun on different drives using policies](/article/autorun-policies.html)  
 Related [Configure Drive Letter for the CD-ROM drive](/article/assign-drive-letter.html)  
  
 More Info [Microsoft: Autoplay Repair Wizard (AutoFix.exe)](http://www.microsoft.com/downloads/details.aspx?FamilyID=c680a7b6-e8fa-45c4-a171-1b389cfacdad)  
 More Info <a href="https://www.bing.com/search?q=KB%20155217%20Q155217" rel="nofollow" title="How to Enable or Disable Automatically Running CD-ROMs [Q155217]">MS KB155217</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20263480%20Q263480" rel="nofollow" title="Backup Runs Very Slow on IDE-Based (ATAPI) Tape Drives and Verification Operations May Not Work [Q263480]">MS KB263480</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20330135%20Q330135" rel="nofollow" title="The AutoRun or AutoPlay Feature Does Not Work [Q330135]">MS KB330135</a>  