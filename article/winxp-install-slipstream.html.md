---
title: 'Slipstream Service pack before installing Windows XP'
date: '2003-03-01T06:19:32+01:00'
status: publish
permalink: /article/winxp-install-slipstream.html
author: Snakefoot
excerpt: 'Apply the service pack before making the install for a faster and more secure install.'
type: post
id: 487
category:
    - 'Install CD'
tag:
    - free-disk-space
    - slipstream
    - windows-install
post_format: []
tags:
    - 'slipstream,windows-install,free-disk-space'
---
Slipstreaming makes sure all security patches are applied immediately, so one doesn't connect to the Internet the first time unprotected. Also slipstreaming saves disk space as the [ServicePackFiles folder](/article/winnt-wfp.html) doesn't need to be created.

1. Copy the contents of you WinXP CD-ROM to a new folder on your HDD **c:\\winxpcd**
2. Download the [network installation](http://www.microsoft.com/windowsxp/pro/downloads/) of the wanted service pack
3. Create a new folder **c:\\winxpsp**
4. Run the service pack .exe file with the parameter -x and when it asks where to extract point it to **c:\\winxpsp**
   > WindowsXP-KB835935-SP2-ENU.EXE -x
  
  - One can also open the service pack .exe file with WinZip and extract the files to c:\\winxpsp
5. Go to the folder **c:\\winxpsp\\i386\\update** and run:
   > UPDATE.EXE /S:c:\\winxpcd
 
 Note the difference between WinXP SP1 and WiNXP SP1a is that the Microsoft Java engine has been taken out.  
  
 Note when slipstreaming WinXP SP2 on a Win2k machine then one might get a fatal error when running UPDATE.EXE. This can by solved by temporarily renaming c:\\winxpsp\\i386\\update\\setupapi.dll (Will force it to use the Win2k setupapi.dll).  
  
 Related [nlite - The ultimate deployment tool](/article/winnt-nlite.html)  
 Related [Unattended Windows Guide](http://unattended.msfn.org/)  