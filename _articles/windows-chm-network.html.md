---
title: 'Allow viewing of CHM files across the network'
date: '2006-10-10T00:13:48+02:00'
permalink: /article/windows-chm-network.html
author: Snakefoot
excerpt: 'Microsoft security update MS05-026 blocks for viewing compressed HTML (CHM) files placed on a network drive.'
type: post
id: 290
categories:
    - windows-2003_tips
    - windows-98_tips
    - windows-me_tips
    - windows-xp_tips
    - windows-2000_tips
tags:
    - compressed-html
    - ie-security
---
Microsoft have released a patch to fix a vulnerability in HTML Help (<a href="https://www.bing.com/search?q=KB+896358+Q896358" title="MS05-026: A vulnerability in HTML Help could allow remote code execution" rel="nofollow">MS05-026 (896358)</a>). This patch disables the ability to view Compressed HTML (CHM) files placed on a remote computer, and one will get the following error message:

> *this page cannot be displayed  
>   
>  Action cancelled.  
>   
>  Navigation to the webpage was cancelled.*

 To view the CHM file one have to download the CHM file to the local computer to view it properly. Even if having downloaded the CHM file to the local computer, then one might experience a security warning when opening the CHM file. It is is possible to [unblock](/article/ie-attachment-manager.html) file and avoid the warning.  
  
 If in an environment where the computers (and the users) in the Intranet Zone can be trusted, then one configure the HTML Help viewer to allow viewing of CHM files placed on a local network drive. Create the following registry key:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\HTMLHelp \\1.x \\ItssRestrictions\]  
>  MaxAllowedZone = 1  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20892675%20Q892675" rel="nofollow" title="Certain Web sites and HTML Help features may not work after you install security update 896358 or security update 890175 [Q892675]">MS KB892675</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20896054%20Q896054" rel="nofollow" title="You cannot open remote content by using the InfoTech protocol after you install security update 896358, security update 840315, or Windows Server 2003 Service Pack 1 [Q896054]">MS KB896054</a>

 Credits [HelpScribble.com](http://www.helpscribble.com/)