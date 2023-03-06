---
title: 'Save the WinXP Product Activation before reinstall'
date: '2001-10-01T21:29:27+02:00'
status: publish
permalink: /article/winxp-save-activation.html
author: Snakefoot
excerpt: 'How to backup the state of having performed Windows Product Activation.'
type: post
id: 394
category:
    - Troubleshoot
tag:
    - windows-product-activation
post_format: []
tags:
    - windows-product-activation
---
WinXP introduced the Windows Product Activation (WPA) which is made to prevent casual piracy by requiring one to contact Microsoft after installing the product. One can avoid having to contact Microsoft every time a WinXP reinstall/repair is made.  
  
 When activating the WinXP the following file is created:

> \\WINNT\\SYSTEM32\\wpa.dbl

 You can backup this file so you don't have to contact Microsoft to activate. After a reinstall or repair boot into safe mode and restore the wpa.dbl. Restart into normal mode and it will ask you to activate, press Ok and it will say it is already activated.  
  
 Note that you have to use the same product key, as you used when installing the first time, as the activation is a combination of your product key and your hardware id.  
  
 Note that you can't use this file to Activate other computers, unless they are almost identical to the computer which was Activated.  
  
 Note it is possible to do quick reinstall on top of the existing installation, without loosing any setting (Even the activation). This is done by running this command from the WinXP CD (X:)
 > X:\\i386\\Winnt32 /unattend

 Note if using System Restore to go back to a Restore Point, which was before Windows was activated, then the Activation is lost, though one can try to Restore the backup created by [System Restore](/article/winnt-services-srservice.html).  
  
 Related [Performing an inplace upgrade of WinXP](/article/winnt-repair-install.html).  
 Related [Change WinXP CD Key using WPA](/article/winnt-cd-key.html).  
  
 More Info [MS KB302878](http://support.microsoft.com/kb/302878 "Frequently Asked Questions about Microsoft Product Activation [Q302878]")  
 More Info [MS KB312295](http://support.microsoft.com/kb/312295 "You are prompted to activate Windows every time you restart your computer [Q312295]")  
 More Info [MS Technet: Preserving OEM Pre-Activation when Re-installing Windows XP](http://www.microsoft.com/technet/prodtechnol/winxppro/deploy/oempreac.mspx)  
 More Info [MS Technet: Deploying Windows XP Using Windows Product Activation](http://www.microsoft.com/technet/prodtechnol/winxppro/deploy/wpadepl.mspx)  