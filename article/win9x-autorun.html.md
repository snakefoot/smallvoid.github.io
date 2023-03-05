---
title: 'Configure Autorun for the CD-ROM drives in Windows 9x'
date: '2000-01-01T23:28:54+01:00'
status: publish
permalink: /article/win9x-autorun.html
author: Snakefoot
excerpt: 'Configure whether to automatically launch application when inserting a CD or DVD disk.'
type: post
id: 110
category:
    - Tips
    - Tips
    - Tips
tag:
    - autorun
    - cdrom-drive
    - dvd-drive
post_format: []
tags:
    - 'autorun,cdrom-drive,dvd-drive'
---
It is possible to enable/disable the autorun for a CDROM drive through the device manager.

1. Right click **My Computer** and select **Properties**
2. Select the tab **Device Manager**
3. Right click your CD-ROM drive and select **Properties**
4. Select the tab **Settings**
5. Uncheck **Auto Insert Notification**
 
 More Info [MS KB312475](http://support.microsoft.com/kb/312475 "CD-ROM Does Not Run Automatically After You Insert It into Your CD-ROM or DVD-ROM Drive [Q312475]")  
  
 Note one can disable Autorun for Audio CDs alone:
1. Double click **My Computer**
2. In the menu select **View** and **Folder Options...**
3. Select the tab **File Types**
4. Select the registered file type **AudioCD** and press the **Edit...** button ("Advanced"-button if WinMe)
5. Select the default action (in bold) and press **Set Default** so no action is performed when an Audio CD is inserted
 
 More Info [MS KB126025](http://support.microsoft.com/kb/126025 "How to Disable the Feature That Allows CD-ROMs and Audio CDs to Run Automatically [Q126025]")  
  
 Related [Configure Autorun for different drives using policies](/article/autorun-policies.html)  
 Related [Configure Drive Letter for the CD-ROM drive](/article/assign-drive-letter.html)  