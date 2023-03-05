---
title: 'Change WinXP license before installing'
date: '2002-06-08T21:21:13+02:00'
status: publish
permalink: /article/winxp-license-edition.html
author: Snakefoot
excerpt: 'How to change the Windows XP license by updating the install files, so it will accept a cd-key from a different license.'
type: post
id: 393
category:
    - 'Install CD'
tag:
    - cd-key
    - license
post_format: []
tags:
    - 'license,cd-key'
---
There are 3 types of licenses :

- OEM - Only allows you to do a clean install
- Retail - Allows you to do an upgrade of existing OS
- Volume - Also known as the corporate version
 
 The license type is contained in the install file X:\\i386\\setupp.ini:
 > Pid=55034000

 The 5 first digits of the Pid says what license it is, and the last 3 digits says what license cd-key it accepts.
- OEM - Pid=82503OEM
- Retail - Pid=51882335 / Pid=55274000
- Volume - Pid=51883270 / Pid=51883270
 
 Note it is possible to interchange the license and the cd-key which is required. Ex. one could create retail license accepting OEM keys Pid=51882OEM.  
  
 Note that one cannot change an OEM/Retail version to a corporate version by just changing the Pid. There are other differences in the files included and you will still have to activate it with a corporate key.  
  
 Credits [TheTechGuide.com](http://www.thetechguide.com/)