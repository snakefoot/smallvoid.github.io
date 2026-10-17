---
title: 'Terminal Services Licensing'
date: '2000-07-23T19:44:07+02:00'
permalink: /article/winnt-services-termservlicensing.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Terminal Services Licensing service.'
type: post
id: 606
categories:
    - windows-2000_services
    - windows-2003_services
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

 More Info <a href="https://www.bing.com/search?q=KB%20232520%20Q232520" rel="nofollow" title="Description of Terminal Services License Server Discovery [Q232520]">MS KB232520</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20237801%20Q237801" rel="nofollow" title="Windows 2000 Terminal Services Requires Licensing Service [Q237801]">MS KB237801</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20237811%20Q237811" rel="nofollow" title="How to Activate a Terminal Services License Server and Install CALs Over the Internet [Q237811]">MS KB237811</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20239107%20Q239107" rel="nofollow" title="Establishing Preferred Windows 2000 Terminal Services License Server [Q239107]">MS KB239107</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20261110%20Q261110" rel="nofollow" title="Windows 2000 Terminal Services in Windows NT 4.0 Domain Cannot Find Windows 2000 Terminal Services Licensing Server [Q261110]">MS KB261110</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20305089%20Q305089" rel="nofollow" title="How to enable debug logging for Terminal Services Licensing [Q305089]">MS KB305089</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20306578%20Q306578" rel="nofollow" title="HOW TO: Deactivate or Reactivate a License Server Using Terminal Services Licensing (Win2k) [Q306578]">MS KB306578</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20306622%20Q306622" rel="nofollow" title="HOW TO: Activate a License Server by Using Terminal Services Licensing in Windows 2000 [Q306622]">MS KB306622</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20310122%20Q310122" rel="nofollow" title="Terminal Services Licensing Service May Not Start and Event ID 43 May Be Logged [Q310122]">MS KB310122</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20325869%20Q325869" rel="nofollow" title="HOW TO: Activate a License Server By Using Terminal Server Licensing in Windows Server 2003 [Q325869]">MS KB325869</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20814593%20Q814593" rel="nofollow" title="HOW TO: Deactivate or Reactivate a License Server By Using Terminal Services Licensing (Win2k3) [Q814593]">MS KB814593</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20839878%20Q839878" rel="nofollow" title="You cannot install the Terminal Services CAL pack on a Windows 2000 Server-based computer [Q839878]">MS KB839878</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20887443%20Q887443" rel="nofollow" title="Event 17 is recorded in the System log on a Windows 2000 Server-based computer that is running Terminal Services Licensing Server [Q887443]">MS KB887443</a>  
  
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