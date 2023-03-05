---
title: 'Configure master browser election in Windows NT'
date: '2001-10-26T22:29:37+02:00'
status: publish
permalink: /article/winnt-master-browser.html
author: Snakefoot
excerpt: 'How to configure the way Microsoft Windows participates in the master browser election.'
type: post
id: 205
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - master-browser
    - microsoft-network
    - windows-domain
post_format: []
tags:
    - 'master-browser,microsoft-network,windows-domain'
---
One can control how a computer participate in the Master Browser election, with these STRING registry keys :

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Browser \\Parameters\]  
>  MaintainServerList = "Auto" (Pro = "Auto", Server = "Yes", Off = "No")  
>  IsDomainMaster = "True" (On = "True", Off = "False", Default = "False")

 The MaintainServerList controls if it should participate in the election at all.  
 The IsDomainMaster gives the computer a higher priority in the election.  
  
 Note to discover/detect the current master browser on the network use the reskit tools browmon or browstat.  
  
 Note if the service [Computer Browser](/article/winnt-services-browser.html) is disabled then the computer will not participate in the election. Setting MaintainServerList = No will keep the Browser service from starting, any attempt will give the following error:  
> *A service specific error occurred: 2550.  
>   
>  More help is available by typing NET HELPMSG 3547*    
>  More Info [MS KB112595](http://support.microsoft.com/kb/112595 "Service Control Manager Event 7024 (2550) [Q112595]")

 Related [Description of Master Browser in the Microsoft Network](/article/windows-master-browser.html)  
 Related [Hide your computer from the network](/article/winnt-hide-network.html)  
  
 More Info [MS KB136712](http://support.microsoft.com/kb/136712 "Common Questions About Browsing with Windows [Q136712]")  
 More Info [MS KB191611](http://support.microsoft.com/kb/191611 "Symptoms of Multihomed Browsers [Q191611]")  
 More Info [MS KB818092](http://support.microsoft.com/kb/818092 "Description of NetBIOS Browsing Console (Browcon.exe) [Q818092]") (Includes browstat)  
  
 Credits [pureperformance.com](http://pureperformance.com/)