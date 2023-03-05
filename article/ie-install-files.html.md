---
title: 'Download install files for Internet Explorer 5 or 6'
date: '2000-01-01T23:04:55+01:00'
status: publish
permalink: /article/ie-install-files.html
author: Snakefoot
excerpt: 'The install files for Internet Explorer can be downloaded to perform offline installation.'
type: post
id: 313
category:
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - install
post_format: []
tags:
    - install
---
When installing Internet Explorer(IE), some might not get the option of just downloading the files. Which is nice when needing to reinstall later or install on several machines since not needing to download the files several times.  
  
 For IE 5:

> ie5setup.exe /c:"ie5wzd.exe /d /s:""#E"

 For IE 6:
 
> ie6setup.exe /c:"ie6wzd.exe /d /s:""#E"

 Note if you replace "/d" with "/d:1" then you will download for all operating systems.  
  
 More Info [MS KB257249](http://support.microsoft.com/kb/257249 "Download-Only Setup of Internet Explorer on Windows 2000 and Windows XP [Q257249]")  
 More Info [IEAK](http://www.microsoft.com/windows/ieak/ "Internet Explorer Administration Kit")  