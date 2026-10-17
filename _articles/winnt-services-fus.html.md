---
title: 'Fast User Switching Compatibility'
date: '2003-06-05T03:03:40+02:00'
permalink: /article/winnt-services-fus.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Fast User Switching Compatibility service.'
type: post
id: 545
categories:
    - windows-xp_services
tags:
    - fast-user-switching
    - terminal-services
    - welcome-screen
---
##### Description:

 Allows several users to be simultaneously logged locally on the same machine, and then switch between each of these user's sessions.  
 The service is only started when a second user logs on to the machine.  
  
 To configure Fast User Switching go to Control Panel -&gt; User Accounts -&gt; "Change the way users log on or off".  
  
 Note Fast User Switching is only available when in a workgroup (Not when part of a domain), and it requires that [Welcome Screen](/article/winxp-welcome-screen.html) and [Terminal Services](/article/winnt-services-termservice.html) are enabled.  
  
 Note the Fast User Switching can consume a lot of memory and CPU power, if one switches between users without closing down the open applications. Making the computer slow to work with.  
  
 More Info <a href="https://www.bing.com/search?q=KB+279765+Q279765" rel="nofollow" title="HOW TO: Use the Fast User Switching Feature in Windows XP [Q279765]">MS KB279765</a>  
 More Info <a href="https://www.bing.com/search?q=KB+279782+Q279782" rel="nofollow" title="Difference Between Log Off and Switch User Commands [Q279782]">MS KB279782</a>  
 More Info <a href="https://www.bing.com/search?q=KB+290249+Q290249" rel="nofollow" title="Programs Display Incorrectly After You Use Fast User Switching [Q290249]">MS KB290249</a>  
 More Info <a href="https://www.bing.com/search?q=KB+294739+Q294739" rel="nofollow" title="A Discussion About the Availability of the Fast User Switching Feature [Q294739]">MS KB294739</a>  
 More Info <a href="https://www.bing.com/search?q=KB+294855+Q294855" rel="nofollow" title="Description of the Fast User Switching Compatibility Service [Q294855]">MS KB294855</a>  
 More Info <a href="https://www.bing.com/search?q=KB+312058+Q312058" rel="nofollow" title="Windows XP May Slow Down If Users Are Logged On with Fast User Switching [Q312058]">MS KB312058</a>  
 More Info <a href="https://www.bing.com/search?q=KB+322861+Q322861" rel="nofollow" title="PRB: Poor Video Performance After a Fast User Switching Operation [Q322861]">MS KB322861</a>  
 More Info <a href="https://www.bing.com/search?q=KB+331841+Q331841" rel="nofollow" title="PRB: Fast User Switching May Be Unavailable on Systems That Use Shared Video Memory [Q331841]">MS KB331841</a>  
  
##### Recommended State:

- Manual, and it will only be activated when a fast user switch is requested.

##### Default State:

- Manual.

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (FastUserSwitchingCompatibility)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Terminal Services](/article/winnt-services-termservice.html)