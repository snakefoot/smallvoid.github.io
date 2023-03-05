---
title: 'Windows 95 Power Toys'
date: '2000-01-01T00:55:53+01:00'
status: publish
permalink: /article/win95-power-toys.html
author: Snakefoot
excerpt: 'Power Toys are small utilities created by Microsoft to make life easier.'
type: post
id: 118
category:
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag:
    - compressed-folders
    - copy-path
    - file-copy
    - powertoys
    - sendto
post_format: []
tags:
    - 'powertoys,copy-path,file-copy,compressed-folders,sendto'
---
[Windows 95 Power Toys](http://www.microsoft.com/windows95/downloads/contents/wutoys/w95pwrtoysset/default.asp) by Microsoft ([Download Mirror of W95PowerToy.exe](http://download.microsoft.com/download/5/2/e/52e8fd68-e528-4995-abe2-5644583536e1/w95powertoy.exe)) is a bunch of utilities created for Win95/WinNT4. It contain several useful items:
- TweakUI to configure your desktop ([Updated Tweak UI ver. 1.33](/article/windows-tweakui.html))
- CAB-View to access CAB files like [compressed folders](/article/windows-compressed-folders.html).
- SendTo X which adds a "Send to any folder"- and a "Send path to clipboard"-shortcut in the [SendTo folder](/article/sendto-shortcut.html) (very handy) 
  - Tried installing SendToX on Win2k and it works great. More Info [MS KB168113](http://support.microsoft.com/kb/168113 "Using Windows 95 PowerToys with Windows NT 4.0 [Q168113]")
- Command Prompt Here that extends the context menu for file folders, so one can open a command prompt in the specified folder.
 
 To install the utilities one have to extract the contents of the file, and right click the different INF-files and select "Install".  
  
 Note the powertoys "Send to mail" cannot co-exist with "Desktop (create shortcut)" / "Send to Desktop as Shortcut". To disable "Send to mail" in powertoys:
1. Open **Control Panel** and double-click **Add/Remove programs**
2. Select the **Send To Extension Power Toys** and click **Add/Remove**-button
3. Clear the checkboxes for the 3 mail extensions
4. Run the following command:
   > regsvr32 sendmail