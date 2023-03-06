---
title: 'QChain to install several hotfixes without restarting'
date: '2001-01-01T15:05:51+01:00'
status: publish
permalink: /article/winnt-qchain-hotfix.html
author: Snakefoot
excerpt: 'QChain is created by Microsoft and allows several hotfixes to be chained together in a single install.'
type: post
id: 495
category:
    - Utilities
    - Utilities
    - Utilities
tag:
    - hotfix
    - 'Windows Update'
post_format: []
tags:
    - 'hotfix,windows-update'
---
[QChain](http://www.microsoft.com/downloads/details.aspx?amp;displaylang=en&familyid=3C64D889-74F1-490B-A2FB-F15671A3B60C) makes it possible to install several hotfixes without needing to reboot after each hotfix. Useful when doing a reinstall of everything.
> \\Q123456\_w2k\_sp2\_x86.exe -z -m  
> \\Q123321\_w2k\_sp2\_x86.exe -z -m  
> \\Q123789\_w2k\_sp2\_x86.exe -z -m  
> \\Qchain.exe

 More Info [MS KB296723](http://support.microsoft.com/kb/296723 "Hotfixes That Are Listed in the [SetupHotFixesToRun] Section in the Svcpack.inf File Are Not Installed [Q296723]") (About flaw in Pre Win2k SP3 Hotfixes)  
 More Info [MS KB296861](http://support.microsoft.com/kb/296861 "How to Install Multiple Windows Updates or Hotfixes with Only One Reboot [Q296861]")  
 More Info [MS KB815062](http://support.microsoft.com/kb/815062 "The Correct File Is Not Installed When You Chain Multiple Hotfixes [Q815062]") (About flaw in [old version](http://www.microsoft.com/downloads/release.asp?ReleaseID=29821))  