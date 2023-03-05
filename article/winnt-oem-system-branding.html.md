---
title: 'Change OEM branding of the system information applet'
date: '2007-07-02T07:44:21+02:00'
status: publish
permalink: /article/winnt-oem-system-branding.html
author: Snakefoot
excerpt: 'The System Information applet can be modified to display OEM name and logo.'
type: post
id: 645
category:
    - Desktop
tag:
    - branding
    - oem
    - system-information
post_format: []
tags:
    - 'branding,oem,system-information'
---
When opening the System Information applet then it can display the name and logo of the computer company that manufactured the computer.

![](/tweak/winnt/pictures/vista-system-information.jpg)

 It is possible to change or add details to the System Information applet with these registry string settings (REG\_SZ):
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\OEMInformation\]
> 
> - Logo - Path to the .bmp file of the manufacturer logo ex. "C:\\Windows\\System32\\OemInfo.bmp". The image dimension should be 120 \* 120 pixels or else the image will be scaled to that size.
> - Manufacturer - Name of the manufacturer.
> - Model - Name of the computer model.
> - SupportHours - Hours that support is available from an OEM.
> - SupportPhone - Telephone number(s) for support for an OEM.
> - SupportURL - URL of the support Web site for an OEM.

 Related [Configure the branding of Internet Explorer](/article/ie-branding.html)  
  
 Credits [Winhelponline.com](http://www.winhelponline.com/)