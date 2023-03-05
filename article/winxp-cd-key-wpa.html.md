---
title: 'Change WinXP CD Key using WPA'
date: '2002-06-08T21:11:56+02:00'
status: publish
permalink: /article/winxp-cd-key-wpa.html
author: Snakefoot
excerpt: 'By re-activating Windows XP then one gets the option to change the cd-key.'
type: post
id: 392
category:
    - Tips
tag:
    - cd-key
    - windows-product-activation
post_format: []
tags:
    - 'cd-key,windows-product-activation'
---
It is possible to change the WinXP CD Key without reinstalling completely.

1. Run System Restore to create a new Checkpoint. So that you can rollback if something goes wrong
2. Start regedit and change at least one digit of the "oobetimer" value:
   > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT\\CurrentVersion \\WPAEvents\]  
   >  oobetimer = ? (Change at least one digit)
3. Start the Windows Product Activation (WPA) screen by running this command:
   > %systemroot%\\system32\\oobe\\msoobe.exe /a
4. At the activation screen, select the option to "Activate by Phone"
5. At the product key change screen, type in your new product key (Make sure to use a key which match your Windows license)
6. If it returns to the activation screen, after typing in the new key, click "Remind me later"
7. Close the window and reboot the machine
8. After the reboot run the command to start the Activation Screen again and make sure that it says "Windows is already activated"
 
 Note the new CD-Key has to match the license of the installation. If having installed a WinXP Pro Corporate Edition (Pirated Version), then the new CD-key must be a corporate CD-key (And not a Retail or OEM CD-key).  
  
 More Info [MS KB328874](http://support.microsoft.com/kb/328874 "HOW TO: Change the Volume Licensing Product Key on a Windows XP SP1-Based Computer [Q328874]")  
 More Info [MS KB842196](http://support.microsoft.com/kb/842196 ""The Product Key used to install Windows is invalid" error message when you try to install a Windows update in Windows Server 2003 [Q842196]")  
 More Info [MS KB918342](http://support.microsoft.com/kb/918342 "How to change the Volume Licensing product key on a Windows XP-based or a Windows Server 2003-based computer [Q918342]")  
  
 Related [Change WinXP license before installing](/article/winxp-license-edition.html)  
 Related [Retrieve a lost CD-Key from registry](/article/winnt-cd-key.html)  
 Related [Save the WinXP Product Activation before reinstall](/article/winxp-save-activation.html)  
  
 Credits [Bink.nu](http://bink.nu/)