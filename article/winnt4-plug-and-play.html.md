---
title: 'Activate plug and play device detection in Windows NT4'
date: '2000-01-01T23:30:10+01:00'
status: publish
permalink: /article/winnt4-plug-and-play.html
author: Snakefoot
excerpt: 'Windows NT4 supports by default not plug and play devices, but Microsoft have created an unsupported driver.'
type: post
id: 465
category:
    - Troubleshoot
tag:
    - plug-and-play
    - pnp
post_format: []
tags:
    - 'pnp,plug-and-play'
---
Windows NT4 does not by default support plug and play (pnp) devices, but it is possible to install a driver which can enable Windows NT4 to detect (but not configure) the registered plug and play devices in the motherboard BIOS.

1. Locate the **Pnpisa.inf** file in the Drvlib\\Pnpisa\\&lt;processor-type&gt; folder (ex. x86) on the Windows NT 4.0 CD-ROM.
2. Right-click the Pnpisa.inf file, and then click **Install** on the menu that appears.
3. Restart your computer.
 
 Related [USB driver for Windows NT4](/article/winnt4-usb-driver.html)  
  
 More Info [MS KB156344](http://support.microsoft.com/kb/156344 "Plug and Play Devices Not Detected or Installed [Q156344]")  
 More Info [MS KB249724](http://support.microsoft.com/kb/249724 ""Error -536870389" When Attempting to Install a SCSI Driver [Q249724]")  