---
title: 'IMAPI CD-Burning COM Service'
date: '2003-06-05T02:11:57+02:00'
status: publish
permalink: /article/winnt-services-imapiservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the IMAPI CD-Burning COM service.'
type: post
id: 551
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Supports the burning of CD-ROM/RW through the IMAPI (Image Mastering Applications Programming Interface) without the need of 3rd party burning software, and used by Microsoft Media Player. (Also used by [WinXP PowerToy ISO Burner](/article/winxp-power-toys.html))  
  
 Note to enable the builtin CD Burner for a limited user, one have to enable the setting "Devices: Allowed to format and eject removable media":
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  AllocateDASD = 2 (0 = Administrators only, 1 = Power Users, 2 = Normal Users)  
>   
>  More Info [MS KB256592](http://support.microsoft.com/kb/256592 "Error Messages When You Try to Eject, Format, or Label a Removable Disk [Q256592]")

 Note if trying to burn/write a DVD-RAM in a DVD-RAM / CD-RW-Combo-Drive, then one have to open **My Computer**, right click the DVD-drive and select **Properties**, select **Recording**-tab and uncheck **Enable CD recording on this drive**, or else one will get this error (Because it tries to access the DVD as a CD-ROM):
> *The disc in the drive is not a writable CD or it is full.  
>   
>  Please insert a blank, writable CD into drive D:\\, or insert a disc with enough free space to hold all the files you have selected for writing to CD.*  
>   
>  More Info [MS KB826510](http://support.microsoft.com/kb/826510 "PRB: You Cannot Write to a DVD-RAM Disc That Is in a DVD-RAM/CD-RW Combination Drive [Q826510]")

 Note if the CD-Writer is only recognized as a CD-ROM drive, then it will not allow recording. To force a CD-ROM drive to be recognized as a CD-Writer:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\CD Burning \\Drives \\Volume{GUID}\]  
>  Drive Type = 2 (1 = CD-R, 2 = CD-RW, 3 = CD-ROM)  
>   
>  Note if having more than one CD-/DVD-drive and one is incorrectly detected as a writer, then it might cause the actually CD-/DVD-writer not to function properly.  
>   
>  More Info [MS KB316529](http://support.microsoft.com/kb/316529 "CD-R drive or CD-RW drive is not recognized as a recordable device [Q316529]")

 More Info [MS KB279157](http://support.microsoft.com/kb/279157 "Description of CD-ROM Recording in Windows XP [Q279157]")  
 More Info [MS KB294652](http://support.microsoft.com/kb/294652 "Only One CD-R or CD-RW Disk Drive Can Be Used to Create Compact Discs in Windows XP [Q294652]")  
 More Info [MS KB297015](http://support.microsoft.com/kb/297015 "HOW TO: Copy Music to and from an Audio CD in Windows XP [Q297015]")  
 More Info [MS KB306524](http://support.microsoft.com/kb/306524 "HOW TO: Copy Information to a CD in Windows XP [Q306524]")  
 More Info [MS KB308591](http://support.microsoft.com/kb/308591 "Unable to Burn a CD-ROM By Using a Samsung CD-RW Drive [Q308591]")  
 More Info [MS KB309522](http://support.microsoft.com/kb/309522 "How to Set the Write Speed for a CD-R Drive in Windows XP [Q309522]")  
 More Info [MS KB324129](http://support.microsoft.com/kb/324129 "HOW TO: Troubleshoot Issues That Occur When You Write Data to a CD-R or CD-RW Optical Disc in Windows XP [Q324129]")  
  
##### Recommended State:

- Manual, if using the builtin CD writer capabilities.
- Disabled, if using 3rd party CD writer software (To avoid conflicts).

##### Default State:

- WinXP: Manual.
- Win2k3: Disabled.

##### Process Name:

- imapi.exe (ImapiService)

##### Supports:

- None

##### Depends:

- None