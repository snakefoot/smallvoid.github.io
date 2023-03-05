---
title: 'Fast User Switching Compatibility'
date: '2003-06-05T03:03:40+02:00'
status: publish
permalink: /article/winnt-services-fus.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Fast User Switching Compatibility service.'
type: post
id: 545
category:
    - 'Services Guide'
tag:
    - fast-user-switching
    - terminal-services
    - welcome-screen
post_format: []
tags:
    - 'fast-user-switching,welcome-screen,terminal-services'
---
##### Description:

 Allows several users to be simultaneously logged locally on the same machine, and then switch between each of these user's sessions.  
 The service is only started when a second user logs on to the machine.  
  
 To configure Fast User Switching go to Control Panel -&gt; User Accounts -&gt; "Change the way users log on or off".  
  
 Note Fast User Switching is only available when in a workgroup (Not when part of a domain), and it requires that [Welcome Screen](/article/winxp-welcome-screen.html) and [Terminal Services](/article/winnt-services-termservice.html) are enabled.  
  
 Note the Fast User Switching can consume a lot of memory and CPU power, if one switches between users without closing down the open applications. Making the computer slow to work with.  
  
 More Info [MS KB279765](http://support.microsoft.com/kb/279765 "HOW TO: Use the Fast User Switching Feature in Windows XP [Q279765]")  
 More Info [MS KB279782](http://support.microsoft.com/kb/279782 "Difference Between Log Off and Switch User Commands [Q279782]")  
 More Info [MS KB290249](http://support.microsoft.com/kb/290249 "Programs Display Incorrectly After You Use Fast User Switching [Q290249]")  
 More Info [MS KB294739](http://support.microsoft.com/kb/294739 "A Discussion About the Availability of the Fast User Switching Feature [Q294739]")  
 More Info [MS KB294855](http://support.microsoft.com/kb/294855 "Description of the Fast User Switching Compatibility Service [Q294855]")  
 More Info [MS KB312058](http://support.microsoft.com/kb/312058 "Windows XP May Slow Down If Users Are Logged On with Fast User Switching [Q312058]")  
 More Info [MS KB322861](http://support.microsoft.com/kb/322861 "PRB: Poor Video Performance After a Fast User Switching Operation [Q322861]")  
 More Info [MS KB331841](http://support.microsoft.com/kb/331841 "PRB: Fast User Switching May Be Unavailable on Systems That Use Shared Video Memory [Q331841]")  
  
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