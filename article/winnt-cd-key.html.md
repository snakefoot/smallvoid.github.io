---
title: 'Retrieve a lost CD-Key from the registry'
date: '2003-02-28T21:03:10+01:00'
status: publish
permalink: /article/winnt-cd-key.html
author: Snakefoot
excerpt: 'Where to find the cd-key for the current Windows install.'
type: post
id: 391
category:
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - cd-key
post_format: []
tags:
    - cd-key
---
The CD-key entered during installation is stored in the registry (and cannot be found on the install CD). One can extract the CD-key of an existing installation, though in the later versions of Windows the CD key has become encrypted. But [KeyFinder](/article/cd-key-registry.html) can decrypt it and recover it no matter what.  
  
 In WinNT4 one can find it as pure text:

> \[HKEY\_LOCAL\_MACHINE\\ Software\\ Microsoft\\ Windows NT \\CurrentVersion\]  
>  ProductID=  
>   
>  Note if the ProductId has the format "12345-nnn-nnnnnnn-12345" then "nnn-nnnnnnn" is the CD-Key.

 In Win2k/WinXP the key is located here but is encrypted:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion\]  
>  DigitalProductId=

 If the Win2k/WinXP was installed unattended then the cd-key might be found here:
 > %SystemRoot%\\System32\\$WINNT$.INF

 Related [Change WinXP CD Key using WPA](/article/winxp-cd-key-wpa.html)