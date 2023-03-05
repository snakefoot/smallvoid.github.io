---
title: 'Disable detection of non-existing IDE devices at every boot'
date: '2001-03-20T01:09:03+01:00'
status: publish
permalink: /article/winnt-ide-detection.html
author: Snakefoot
excerpt: 'Faster boot times by not spending time on detecting non-existing IDE devices.'
type: post
id: 375
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - ATA
    - boot-time
    - cdrom-drive
    - dvd-drive
    - hard-disk-drive
    - IDE
post_format: []
tags:
    - 'IDE,ATA,hard-disk-drive,cdrom-drive,dvd-drive,boot-time'
---
Every time Windows boots it will check the onboard controller if there is any drives attached. If you don't have the habit of swapping IDE units in and out or you have none installed at all, then you might want to disable the scanning for non-existing IDE units and get a faster bootup.

1. Open Control Panel and double-click System
2. Choose the Hardware-tab and click Device Manager button
3. Select the IDE ATA/ATAPI Controllers-node and double click your Primary- and Secondary-Channel and go to Advanced Settings
4. Change the Device Type from "Auto detection" to "None" when there is no IDE Unit attached.
 
 Related [Configue IDE ATA hard disk to use DMA transfer](/article/winnt-ide-dma.html)  
 Related [Uninstall ghost devices or services in Win2k/XP](/article/winnt-ghost-devices.html)  
  
 Credits [rojakpot.com](http://www.rojakpot.com/)