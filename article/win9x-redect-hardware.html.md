---
title: 'Force Windows 9x to redetect all hardware'
date: '2001-01-01T02:46:56+01:00'
status: publish
permalink: /article/win9x-redect-hardware.html
author: Snakefoot
excerpt: 'Make Windows 9x redetect all hardware in case one is migrating to a new computer.'
type: post
id: 139
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - device-manager
    - drivers
    - hardware
post_format: []
tags:
    - 'hardware,drivers,device-manager'
---
Win9x keeps track of all hardware in your machine, which can be seen in the Device Manager. Sometimes Win9x gets confused by all your hardware and starts to act strange. One can clear this confusion and hopefully it will solve any problems.  
  
 By deleting the this registry-key, Win9x will forget all information about hardware and at next boot it will start redecting everything :

> \[HKEY\_LOCAL\_MACHINE \\Enum\]

 Note if Windows doesn't start detecting new devices after first boot, then go to Control Panel -&gt; Add/Remove Hardware and force a scan for new hardware.  
  
 Note doing this will cause Windows to forget your network settings, and you might manually have to reinstall your Dial-Up Adapter. But it will remember the dial-up connection to your ISP along with userid and password.  
  
 Note before doing starting the detecting it is a good idea to have all necessary driver disks ready along with the Windows CD-ROM in case it cannot reuse the drivers which currently resides in the Windows directory.  
  
 Note it might be a good idea to [Check for ghost devices](/article/win9x-ghost-devices.html) after redetecting and installing all devices.  
  
 Note one can use this solution to migrate Win9x from an old computer to a new computer. Before moving the HDD into the new computer just delete the registry folder shown above. Though this solution doesn't come near the perfection of a clean format and install, but it is quicker and keeps the settings and applications.