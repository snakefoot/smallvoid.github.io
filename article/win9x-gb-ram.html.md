---
title: 'Configure Windows 9x to handle more than 1 GB RAM'
date: '2002-06-19T00:12:28+02:00'
status: publish
permalink: /article/win9x-gb-ram.html
author: Snakefoot
excerpt: 'Make it possible to run Windows 9x with 1 GByte RAM (or more).'
type: post
id: 172
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag: []
post_format: []
tags:
    - ''
---
Windows 95 / 98 / Me has a limitation for how much memory they can handle, actual if having 1 GByte (1024 MByte) or more, then it might keep Win9x from starting at all. And give messages like these or reboot continuously:

> *There is not enough memory available to run this program. Quit one or more programs, and then try again.  
>   
>  Insufficient memory to initialize windows. Quit one or more memory-resident programs or remove unnecessary utilities from your Config.sys and Autoexec.bat files, and restart your computer.*

 To solve this, do one of the following :
- Take out your memory and only use 512 Mbyte.
- Limit the [VCACHE](/article/win9x-disk-cache.html) to a maximum of 512 MByte. As it is not able to configure itself properly with large amount of memory available.
- Limit the available memory for Windows to use to 768 MByte.  
   Do this by editing the C:\\Windows\\System.ini and add this setting to the \[386enh\] section. > \[386enh\]  
  >  MaxPhysPage=40000
 
 More Info [MS KB304943](http://support.microsoft.com/kb/304943 "Computer May Reboot Continuously with More Than 1.5 GB of RAM [Q304943]")  
 More Info [MS KB253912](http://support.microsoft.com/kb/253912 ""Out of Memory" Error Messages with Large Amounts of RAM Installed [Q253912]")  
 More Info [MS KB184447](http://support.microsoft.com/kb/184447 "Error Message: Insufficient Memory to Initialize Windows [Q184447]")  
 More Info [MS KB181862](http://support.microsoft.com/kb/181862 "Specifying Amount of RAM Available to Windows Using MaxPhysPage [Q181862]")  