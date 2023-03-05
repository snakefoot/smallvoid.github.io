---
title: 'Install Windows 2000 without using CD-Key'
date: '2002-06-08T05:57:20+02:00'
status: publish
permalink: /article/win2k-install-cd-key.html
author: Snakefoot
excerpt: 'By changing the license on the install cd, then one don''t have to supply a cd-key during install.'
type: post
id: 485
category:
    - 'Install CD'
tag:
    - cd-key
post_format: []
tags:
    - cd-key
---
This is done by changing the CD-Key license to be volume/corporate, which doesn't require a CD-Key. The CD-Key license can only be changed like this if having the MSDN CD.  
  
 To change the CD-Key license of you Windows 2000, edit the install file X:\\i386\\setupp.ini :
 > Pid=51873XXX

 Usually the "XXX" is three zeros "000", replace them with "270" (Corporate) so it looks like this :
 > Pid=51873270

 Credits [TheTechGuide.com](http://www.thetechguide.com/)