---
title: 'Configure and troubleshoot Background Intelligent Transfer Service'
date: '2002-08-06T23:55:16+02:00'
status: publish
permalink: /article/winnt-bits-config.html
author: Snakefoot
excerpt: 'Control how much of the bandwidth the Background Intelligent Transfer Service (BITS) is allowed to use.'
type: post
id: 526
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag: []
post_format: []
tags:
    - ''
---
[Background Intelligent Transfer Service (BITS)](/article/winnt-services-bits.html) was extended in Ver. 2 (XP SP2 or [MS KB842773](http://support.microsoft.com/kb/842773 "An update package that includes BITS 2.0 and WinHTTP 5.1 is available for Windows Server 2003, for Windows XP, and for Windows 2000 [Q842773]")) so it can throttle the use of bandwidth by using the following policies:
- **Enable/Disable throttling of network traffic:**
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Policies \\Microsoft \\Windows \\BITS\]  
  >  EnableBITSMaxBandwidth = 0 (1 = Imposes limit, 0 = Uses no limit, Default = 0)
- **Max bandwidth (kbps) to use in working hours:**
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Policies \\Microsoft \\Windows \\BITS\]  
  >  MaxTransferRateOnSchedule = 50 (Default = 50 kbps)
- **Max bandwidth (kbps) to use in non-working hours:**
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Policies \\Microsoft \\Windows \\BITS\]  
  >  MaxTransferRateOffSchedule = 0xffffffff (Default = Unlimited)  
  >  UseSystemMaximum = 0 (0 = Impose limit in non-working hours, 1 - Ignore limit)
- **Control the working hour period:**
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Policies \\Microsoft \\Windows \\BITS\]  
  >  MaxBandwidthValidFrom = 8 (Hour of the day the working schedule begins, Default = 8)  
  >  MaxBandwidthValidTo = 18 (Hour of the day the working schedule ends, Default = 18)