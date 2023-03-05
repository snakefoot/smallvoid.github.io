---
title: 'Terminal Services Licensing'
date: '2000-07-23T19:44:07+02:00'
status: publish
permalink: /article/winnt-services-termservlicensing.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Terminal Services Licensing service.'
type: post
id: 606
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - terminal-services
post_format: []
tags:
    - terminal-services
---
##### Description:

 The Terminal Services License Service stores the Client Access Licenses (CALs) that have been issued for a Terminal server, and tracks the licenses that have been issued to client computers or terminals. If this service is turned off, the server will be unavailable to issue Terminal Server licenses to clients when they are requested. If another License Server is discoverable on a DC in the forest, the requesting Terminal Server will attempt to use it.  
  
 Note in Win2k if the [Protected Storage](/article/winnt-services-protectedstorage.html) have become corrupt, then it might fail to start and give this error message:
> *Event ID: 7024  
>  Description: The Terminal Services Licensing service terminated with service-specific error 3221291009.  
>   
>  Event ID: 37  
>  Description: Can't start Terminal Services Licensing because of error 'Can't initialize Cryptographic - error code 80090016.'*

 More Info [MS KB232520](http://support.microsoft.com/kb/232520 "Description of Terminal Services License Server Discovery [Q232520]")  
 More Info [MS KB237801](http://support.microsoft.com/kb/237801 "Windows 2000 Terminal Services Requires Licensing Service [Q237801]")  
 More Info [MS KB237811](http://support.microsoft.com/kb/237811 "How to Activate a Terminal Services License Server and Install CALs Over the Internet [Q237811]")  
 More Info [MS KB239107](http://support.microsoft.com/kb/239107 "Establishing Preferred Windows 2000 Terminal Services License Server [Q239107]")  
 More Info [MS KB261110](http://support.microsoft.com/kb/261110 "Windows 2000 Terminal Services in Windows NT 4.0 Domain Cannot Find Windows 2000 Terminal Services Licensing Server [Q261110]")  
 More Info [MS KB305089](http://support.microsoft.com/kb/305089 "How to enable debug logging for Terminal Services Licensing [Q305089]")  
 More Info [MS KB306578](http://support.microsoft.com/kb/306578 "HOW TO: Deactivate or Reactivate a License Server Using Terminal Services Licensing (Win2k) [Q306578]")  
 More Info [MS KB306622](http://support.microsoft.com/kb/306622 "HOW TO: Activate a License Server by Using Terminal Services Licensing in Windows 2000 [Q306622]")  
 More Info [MS KB310122](http://support.microsoft.com/kb/310122 "Terminal Services Licensing Service May Not Start and Event ID 43 May Be Logged [Q310122]")  
 More Info [MS KB325869](http://support.microsoft.com/kb/325869 "HOW TO: Activate a License Server By Using Terminal Server Licensing in Windows Server 2003 [Q325869]")  
 More Info [MS KB814593](http://support.microsoft.com/kb/814593 "HOW TO: Deactivate or Reactivate a License Server By Using Terminal Services Licensing (Win2k3) [Q814593]")  
 More Info [MS KB839878](http://support.microsoft.com/kb/839878 "You cannot install the Terminal Services CAL pack on a Windows 2000 Server-based computer [Q839878]")  
 More Info [MS KB887443](http://support.microsoft.com/kb/887443 "Event 17 is recorded in the System log on a Windows 2000 Server-based computer that is running Terminal Services Licensing Server [Q887443]")  
  
##### Recommended State:

- Disabled.

##### Default State:

- Win2k Srv: Automatic.
- Win2k Pro: Not available.

##### Process Name:

- LServer.exe (termservlicensing)

##### Supports:

- None

##### Depends:

- [Event Log](/article/winnt-services-eventlog.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)