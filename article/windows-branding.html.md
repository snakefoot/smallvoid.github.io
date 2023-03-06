---
title: 'Change OEM branding of System Properties'
date: '2003-09-11T21:48:29+02:00'
status: publish
permalink: /article/windows-branding.html
author: Snakefoot
excerpt: 'System Properties can be modified to display company name or company pictures.'
type: post
id: 299
category:
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
tag:
    - branding
    - oem
post_format: []
tags:
    - 'branding,oem'
---
It is possible to change some of the text shown on **System Properties**, which is shown when right clicking **My Computer** and selecting **Properties**.

1. Go to the folder **%Windir%\\System**
2. Create a new text file and name it **OemInfo.ini**
3. Edit the new text file and insert the following lines (Modify them as you wish)
  > \[general\]  
  >  Manufacturer=Dell  
  >  Model=XPS200s  
  >   
  >  \[Support Information\]  
  >  Line1=These lines will be  
  >  Line2=shown when pressing  
  >  Line3=the button "Support Information"  
  >  Line4=  
  >  Line5=Cheers
 
 It is also possible to place a nice logo on the System Properties:
1. Find a good BMP picture in 256 color and make sure it has the right size: 
  - Win9x: 96 x 96 pixels (Small fonts), 120 x 120 pixels (Large fonts)
  - Win2k/XP: 172 x 172 pixels
2. Copy the picture to **%Windir%\\System** and rename it to **OemInfo.bmp**
 
 Note it is also possible to place the two files in **%Windir%\\System32** if on a WinNT+ installation.  
  
 More Info [MS KB216347](http://support.microsoft.com/kb/216347 "HOWTO: Test and Modify the Logos in an OEM Preinstallation [Q216347]")  
 More Info [MS KB218176](http://support.microsoft.com/kb/218176 "How to Alter Logo Information on the System Tool's General Tab [Q218176]")  
 More Info [MS KB250609](http://support.microsoft.com/kb/250609 "INFO: Quick Guide to Preinstalling Windows 2000 [Q250609]")  
 More Info [MS KB314472](http://support.microsoft.com/kb/314472 "Quick Guide to Preinstalling Windows XP [Q314472]")  
  
 Related [Configure the branding of Internet Explorer](/article/ie-branding.html)