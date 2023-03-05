---
title: 'Changing the font of the command prompt'
date: '2007-08-28T02:02:41+02:00'
status: publish
permalink: /article/winnt-cmd-add-font.html
author: Snakefoot
excerpt: 'How to use a different font in the command prompt than Lucida Console and Raster Fonts.'
type: post
id: 733
category:
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
tag:
    - font
    - true-type
    - visual-style
post_format: []
tags:
    - 'font,true-type,visual-style'
---
The command prompt font can be changed with the following steps:

1. Open a command prompt (cmd.exe) and click the left icon in the title bar and select "Properties".
2. Select the "Font"-tab and change the font to the wanted.
 
 By default there are only two fonts the "Raster Fonts" and the true type font "Lucida Console". It is possible to add extra mono spaced fonts to the list like [Bitstream Vera Sans Mono](http://www.gnome.org/fonts/), [Andale Mono](http://prdownloads.sourceforge.net/corefonts/andale32.exe?download) or [Microsoft Consolas](http://www.microsoft.com/downloads/details.aspx?familyid=22e69ae4-7e40-4807-8a86-b3d36fab68d3) ([Mirror](http://smallvoid.orgfree.com/?file=consolas-font-family.msi.zip)).  
  
 To add a new font to the list:
1. Open the registry editor (regedit.exe) and go to this registry key:
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Console \\TrueTypeFont\]  
  >  0 = "Lucida Console"
2. Add a new font to the list by creating a new registry STRING value (REG\_SZ) with the name "00" (Two zeros) . If needing to add a third font then use three zeros etc.
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Console \\TrueTypeFont\]  
  >  0 = "Lucida Console"  
  >  00 = "Consolas"
3. Might have to restart the computer to properly apply the new font in the command prompt.
 
 More Info [MS KB247815](http://support.microsoft.com/kb/247815 "Necessary criteria for fonts to be available in a command window [Q247815]") (Describes the requirements before a font can be used).  
  
 Credits [Duffblog](http://blogs.oracle.com/duffblog/)