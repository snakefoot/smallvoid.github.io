---
title: 'IMAPI CD-Burning COM Service'
date: '2003-06-05T02:11:57+02:00'
permalink: /article/winnt-services-imapiservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the IMAPI CD-Burning COM service.'
type: post
id: 551
categories:
    - windows-2003_services
    - windows-xp_services
tags: []
---
##### Description:

 Supports the burning of CD-ROM/RW through the IMAPI (Image Mastering Applications Programming Interface) without the need of 3rd party burning software, and used by Microsoft Media Player. (Also used by [WinXP PowerToy ISO Burner](/article/winxp-power-toys.html))  
  
 Note to enable the builtin CD Burner for a limited user, one have to enable the setting "Devices: Allowed to format and eject removable media":
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  AllocateDASD = 2 (0 = Administrators only, 1 = Power Users, 2 = Normal Users)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+256592+Q256592" rel="nofollow" title="Error Messages When You Try to Eject, Format, or Label a Removable Disk [Q256592]">MS KB256592</a>

 Note if trying to burn/write a DVD-RAM in a DVD-RAM / CD-RW-Combo-Drive, then one have to open **My Computer**, right click the DVD-drive and select **Properties**, select **Recording**-tab and uncheck **Enable CD recording on this drive**, or else one will get this error (Because it tries to access the DVD as a CD-ROM):
> *The disc in the drive is not a writable CD or it is full.  
>   
>  Please insert a blank, writable CD into drive D:\\, or insert a disc with enough free space to hold all the files you have selected for writing to CD.*  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+826510+Q826510" rel="nofollow" title="PRB: You Cannot Write to a DVD-RAM Disc That Is in a DVD-RAM/CD-RW Combination Drive [Q826510]">MS KB826510</a>

 Note if the CD-Writer is only recognized as a CD-ROM drive, then it will not allow recording. To force a CD-ROM drive to be recognized as a CD-Writer:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\CD Burning \\Drives \\Volume{GUID}\]  
>  Drive Type = 2 (1 = CD-R, 2 = CD-RW, 3 = CD-ROM)  
>   
>  Note if having more than one CD-/DVD-drive and one is incorrectly detected as a writer, then it might cause the actually CD-/DVD-writer not to function properly.  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+316529+Q316529" rel="nofollow" title="CD-R drive or CD-RW drive is not recognized as a recordable device [Q316529]">MS KB316529</a>

 More Info <a href="https://www.bing.com/search?q=KB+279157+Q279157" rel="nofollow" title="Description of CD-ROM Recording in Windows XP [Q279157]">MS KB279157</a>  
 More Info <a href="https://www.bing.com/search?q=KB+294652+Q294652" rel="nofollow" title="Only One CD-R or CD-RW Disk Drive Can Be Used to Create Compact Discs in Windows XP [Q294652]">MS KB294652</a>  
 More Info <a href="https://www.bing.com/search?q=KB+297015+Q297015" rel="nofollow" title="HOW TO: Copy Music to and from an Audio CD in Windows XP [Q297015]">MS KB297015</a>  
 More Info <a href="https://www.bing.com/search?q=KB+306524+Q306524" rel="nofollow" title="HOW TO: Copy Information to a CD in Windows XP [Q306524]">MS KB306524</a>  
 More Info <a href="https://www.bing.com/search?q=KB+308591+Q308591" rel="nofollow" title="Unable to Burn a CD-ROM By Using a Samsung CD-RW Drive [Q308591]">MS KB308591</a>  
 More Info <a href="https://www.bing.com/search?q=KB+309522+Q309522" rel="nofollow" title="How to Set the Write Speed for a CD-R Drive in Windows XP [Q309522]">MS KB309522</a>  
 More Info <a href="https://www.bing.com/search?q=KB+324129+Q324129" rel="nofollow" title="HOW TO: Troubleshoot Issues That Occur When You Write Data to a CD-R or CD-RW Optical Disc in Windows XP [Q324129]">MS KB324129</a>  
  
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