---
title: 'Customize the default registered identity'
date: '2002-10-28T01:01:26+01:00'
permalink: /article/windows-registered-owner.html
author: Snakefoot
excerpt: 'How to change the name and company registered as owner of the Windows installation.'
type: post
id: 276
categories:
    - windows-2003_tips
    - windows-95_tips
    - windows-98_tips
    - windows-me_tips
    - windows-nt4_tips
    - windows-xp_tips
    - windows-2000_tips
tags: []
---
Some times when installing Games and Applications then you get requested to verify that your name and company are correct. The default name and company presented to you each time is set during the installation.  
  
 To change your identify go to the following STRING registry keys :

> \[HKEY\_CURRENT\_USER /Software /Microsoft /MS Setup (ACME) /User Info\]  
>  DefCompany = "UserCompany"  
>  DefName = "UserName"

 To change the owner go to the following STRING registry keys (Win9x only):
> \[HKEY\_LOCAL\_MACHINE /SOFTWARE /Microsoft /Windows /CurrentVersion\]  
>  RegisteredOrganization = "UserCompany"  
>  RegisteredOwner = "UserName"

 To change the owner go to the following STRING registry keys (WinNT+ only):
> \[HKEY\_LOCAL\_MACHINE /SOFTWARE /Microsoft /Windows NT /CurrentVersion\]  
>  RegisteredOrganization = "UserCompany"  
>  RegisteredOwner = "UserName"

 More Info <a href="https://www.bing.com/search?q=KB+88363+Q88363" rel="nofollow" title="How to Change Name and Company After Windows Installation [Q88363]">MS KB88363</a>  
 More Info <a href="https://www.bing.com/search?q=KB+148198+Q148198" rel="nofollow" title="XADM: Where Newprof.exe Gets the Username [Q148198]">MS KB148198</a>  
  
 Credits [neowin.net](http://www.neowin.net/)  