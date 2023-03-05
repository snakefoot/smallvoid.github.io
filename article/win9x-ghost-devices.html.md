---
title: 'Improve system stability by removing ghost devices'
date: '2002-10-26T02:03:55+02:00'
status: publish
permalink: /article/win9x-ghost-devices.html
author: Snakefoot
excerpt: 'Description of ghost devices and how they can be removed in safemode.'
type: post
id: 138
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - boot-time
    - device-manager
    - drivers
    - ghost-devices
    - hardware
post_format: []
tags:
    - 'ghost-devices,device-manager,hardware,drivers,boot-time'
---
Sometimes Win9x gets confused by some hardware which causes it to have duplicate registration of the same device, or still have ghost devices registered which are no longer in the machine. Ghost Devices can cause slow boot and other erratic behavior because Windows tries to communicate with a device which isn't there.  
  
 To check for such abnormalities one should boot into safemode (Press F5 or F8 at boot). When in safemode the Device Manager will show all devices, and not just the active ones. To starte the Device Manager go to Control Panel -&gt; System -&gt; Device Manager.  
  
 Note if the same device is listed multiple times in the Device Manager, then it is usually safe to remove all occurrences of the same device and reboot to let it redetect the actual device properly.  
 Some devices are actually meant to be listed multiple times with the same name ex. "Motherboard Resources", if having removed all occurrences of a device, and at reboot it redetects all the devices again, then just ignore those devices.  
  
 Related [Boot Log Analyzer](/article/win9x-boot-log-analyzer.html)  
 Related [Force Windows to redetect all the hardware](/article/win9x-redect-hardware.html)