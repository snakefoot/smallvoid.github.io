---
title: 'Microsoft Auto Skip Driver Agent'
date: '2000-01-01T22:55:52+01:00'
permalink: /article/win9x-asd-agent.html
author: Snakefoot
excerpt: 'Utility to diagnose what hardware devices have failed to start and have been disabled.'
type: post
id: 166
categories:
    - windows-98_utilities
    - windows-me_utilities
tags:
    - drivers
    - hardware
---
Windows 98/Me includes an utility called ASD (Auto Skip Driver) agent, which enables detection of non-working drivers. If a driver keeps Windows from starting up then the driver is disabled, so next time Windows is started it will hopefully succeed.  
  
 ASD.EXE makes it possible to see what device, which kept Windows from loading the first time (Usually the device is also shown in the Device Manager with an yellow mark). With this information one can download new drivers or BIOS upgrade for the device. ASD.EXE can then be used to activate the device again, and test if the upgraded drivers, BIOS did help.  
  
 Before ASD one had to turn on bootlog.txt and identify what device belonged to the driver which failed to load (Usually the last line in the bootlog.txt), then boot in safemode and disable that device.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20186588%20Q186588" rel="nofollow" title="Description of the Automatic Skip Driver Agent (Asd.exe) Tool [Q186588]">MS KB186588</a>  
  
 Related [Boot log Analyzer](/article/win9x-boot-log-analyzer.html)