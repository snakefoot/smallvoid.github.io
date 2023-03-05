---
title: 'Monitor system performane and system health'
date: '2003-08-23T14:34:03+02:00'
status: publish
permalink: /article/winnt-cpu-temp.html
author: Snakefoot
excerpt: 'CPU core temperature monitoring utilities, that can give alerts if things gets too hot.'
type: post
id: 350
category:
    - Troubleshoot
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag:
    - AMD
    - cpu
    - Intel
    - motherboard
    - performance-monitor
    - SMART
post_format: []
tags:
    - 'performance-monitor,cpu,Intel,AMD,motherboard,SMART'
---
When doing overclocking, then it is very important to monitor CPU temperature, Chipset Temperature, GPU temperature and fan-speeds. By default these details are not displayed by the Windows operating system, though these numbers can be retrieved from the motherboard.  
  
 There are tools that can connect to the probes on the motherboard, and display these numbers, and give alerts if the values gets higher than a certain threshold.

- [SpeedFan](http://www.almico.com/speedfan.php) - Can monitor almost everything (CPU/Chipset/GPU/Fans/Etc.). Can also display [HDD SMART](http://en.wikipedia.org/wiki/S.M.A.R.T.) statistics. Sadly enough it conflicts with [UAC](/article/winnt-user-account-protection.html).
- [CoreTemp](http://www.alcpu.com/CoreTemp/) - Can monitor CPU temperature. Also has a sidebar gadget that works with Vista/Win7. Sadly enough it conflicts with [UAC](/article/winnt-user-account-protection.html).