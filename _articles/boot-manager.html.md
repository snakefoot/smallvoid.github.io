---
title: 'Boot Manager'
date: '2001-01-31T16:11:17+01:00'
permalink: /article/boot-manager.html
author: Snakefoot
excerpt: 'A boot manager can help with running multiple operating systems on the same machine.'
type: post
id: 86
categories:
    - windows-2000-utilities
    - windows-2003-utilities
    - windows-95-utilities
    - windows-98-utilities
    - windows-me-utilities
    - windows-nt4-utilities
    - windows-xp-utilities
    - ms-dos-utilities
    - windows-vista-utilities
tags:
    - boot-manager
    - boot-sector
---
It possible to install several operating systems on the same machine. This requires a boot manager which is able to handle the different boot sectors used by each operating system. The boot sectors can be handled in two ways:

- All the operating system are installed on the same partition and the boot manager controls which boot-sector to load.
- Each operating system are installed on their own primary partition and the boot manager controls which primary partition becomes the active one.
 
 There exists different boot manager to help in this adventure:
- [XOSL](http://www.ranish.com/part/xosl.htm) ([Sourgeforge](http://xosl.sourceforge.net/))
- [GAG - The graphical boot manager](http://gag.sourceforge.net/)