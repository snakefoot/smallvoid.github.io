---
title: 'Configure Autorun for different drives using policies'
date: '2003-01-11T23:36:41+01:00'
status: publish
permalink: /article/autorun-policies.html
author: Snakefoot
excerpt: 'How to configure autorun for the different drive types.'
type: post
id: 111
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - autoplay
    - autorun
    - cdrom-drive
    - hotstart
    - usb
    - usb-stick
post_format: []
tags:
    - 'autorun,cdrom-drive,usb,usb-stick,hotstart,autoplay'
---
Windows is by default configured to poll all devices every second to check if the media has changed since last poll. If the media has changed then it checks if a file named *Autorun.inf* is placed in the root.  
  
 One can configure what drive-letters shouldn't be checked for *Autorun.inf*. Each bit corresponds to a driveletter.

<table border="1"><tr><th>Bit</th><th>Value(Dec)</th><th>Value(Hex)</th><th>Letter</th></tr><tr><td>1</td><td>1</td><td>0x00000001</td><td>A:</td></tr><tr><td>2</td><td>2</td><td>0x00000002</td><td>B:</td></tr><tr><td>3</td><td>4</td><td>0x00000004</td><td>C:</td></tr><tr><td>4</td><td>8</td><td>0x00000008</td><td>D:</td></tr><tr><td>5</td><td>16</td><td>0x00000010</td><td>E:</td></tr><tr><td>etc.</td><td>etc.</td><td>etc.</td><td>etc.</td></tr></table>

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoDriveAutoRun = 0x00000005 (DWORD)  
>   
>  Disables the checking for *Autorun.inf* on A: + C:

 One can configure what drive-types shouldn't be checked for *Autorun.inf*. Each bit corresponds to a drivetype.  
  
<table border="1"><tr><th>Bit</th><th>Value(Dec)</th><th>Value(Hex)</th><th>Type</th></tr><tr><td>1</td><td>1</td><td>0x00000001</td><td>DRIVE\_UNKNOWN</td></tr><tr><td>2</td><td>2</td><td>0x00000002</td><td>DRIVE\_NO\_ROOT\_DIR</td></tr><tr><td>3</td><td>4</td><td>0x00000004</td><td>DRIVE\_REMOVABLE (Floppy etc.)</td></tr><tr><td>4</td><td>8</td><td>0x00000008</td><td>DRIVE\_FIXED (HDD etc.)</td></tr><tr><td>5</td><td>16</td><td>0x00000010</td><td>DRIVE\_REMOTE (Network etc.)</td></tr><tr><td>6</td><td>32</td><td>0x00000020</td><td>DRIVE\_CDROM</td></tr><tr><td>7</td><td>64</td><td>0x00000040</td><td>DRIVE\_RAMDISK</td></tr><tr><td>8</td><td>128</td><td>0x00000080</td><td>Unspecified Reserved Type (Should always be set)</td></tr></table>

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoDriveTypeAutoRun = 0x00000095 (WinNT+ DWORD)  
>  NoDriveTypeAutoRun = 95 00 00 00 (Win9x BINARY)  
>   
>  Disables the checking for the file *Autorun.inf* on "Unspecified Reserved Type" + DRIVE\_REMOTE + DRIVE\_REMOVABLE + DRIVE\_UNKNOWN  
>   
>  Note if disabling autorun for all devices (0x000000FF) then it will also disable the [Vista Hotstart](http://www.microsoft.com/whdc/system/platform/firmware/hotstart.mspx) feature.

 Note there is a little confusion about autorun on USB drives, which have caused the creation of software like [APO Usb Autorun](http://www.archidune.com/apo/):
> *Autorun.inf files are not supported under Microsoft Windows XP for drives that return DRIVE\_REMOVABLE from GetDriveType.* [MSDN](http://msdn.microsoft.com/library/en-us/shellcc/platform/shell/programmersguide/shell_basics/shell_basics_extending/autorun/autoplay_works.asp "Creating an AutoRun-Enabled Application")  
>   
> *The Autorun capabilities are restricted to CD-ROM drives and fixed disk drives. If you need to make a USB storage device perform Autorun, the device must not be marked as a removable media device.* [USB FAQ](http://www.microsoft.com/whdc/device/storage/usbfaq.mspx "USB Storage - FAQ for Driver and Hardware Developers")  
>   
> *The action key is only used in Microsoft Windows XP Service Pack 2 (SP2) or later. It is only supported for drives of type DRIVE\_REMOVABLE and DRIVE\_FIXED. In the case of DRIVE\_REMOVABLE, the action key is required.* [MSDN](http://msdn.microsoft.com/library/en-us/shellcc/platform/shell/programmersguide/shell_basics/shell_basics_extending/autorun/autoplay_cmds.asp "Autorun.inf Entries")

 Note these policies only work on media which are able to contain an *Autorun.inf* file. Media like Audio CDs will not be affected by the setting of these policies.  
  
 Note if one don't want to enable autorun for a single CD-ROM, then instead just hold down the SHIFT key while inserting the CD-ROM.  
  
 Note if having Autorun.inf checking enabled for floppy drives, then it might at random access the floppy drive and grind for a long time searching for the *Autorun.inf*. This grinding can also happen if accidentally having a shortcut pointing to a file placed on A: or B: drive.  
  
 More Info [MS KB136214](http://support.microsoft.com/kb/136214 "How to Test Autorun.inf Files [Q136214]")  
 More Info [MS KB177880](http://support.microsoft.com/kb/177880 "CD-ROM Does Not Run Automatically When Inserted [Q177880]")  
 More Info [MS KB967715](http://support.microsoft.com/kb/967715 "How to correct "disable Autorun registry key" enforcement in Windows")  
  
 To disable the polling of CD-ROM/DVD devices:  
  
 Related [Win9x/Me : Configure Autorun for the CD-ROM drive](/article/win9x-autorun.html)  
 Related [WinNT/2k/Xp : Configure Autorun for the CD-ROM drives](/article/winnt-autorun.html)  
  
 Credits [ashzfall.com](http://ashzfall.com/)