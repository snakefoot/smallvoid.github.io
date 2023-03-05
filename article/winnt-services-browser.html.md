---
title: 'Computer Browser'
date: '2000-06-06T00:04:58+02:00'
status: publish
permalink: /article/winnt-services-browser.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Computer Browser service.'
type: post
id: 528
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - master-browser
    - microsoft-network
post_format: []
tags:
    - 'master-browser,microsoft-network'
---
##### Description:

 Enables the computer to participate in the election for maintaining the [browser list](/article/winnt-master-browser.html).  
  
 The browser list contains all computers, that have [announced](/article/winnt-hide-network.html) themselves on the network through the [Server service](/article/winnt-services-lanmanserver.html)- Home Network: This service only need to be activated on a single computer. It is convenient to activate this service on all computers to avoid single point of failure.
- Corporate Network: The Active Directory should be used instead.
 
 Note even if no computer is maintaining the browser list, then it is still possible to access remote shares by creating direct shortcuts or mapping network shares (\\\\computername\\sharename).  
  
 Note the Computer Browser service will fail to start if the services it depends on are not available (Disable the Computer Browser if not using File Sharing):
> *Event ID: 7003  
>  The Computer Browser service depends on the following nonexistent service: [LanmanServer](/article/winnt-services-lanmanserver.html), [LMHOSTS](/article/winnt-services-lmhosts.html)*

 Note if the Computer Browser cannot be reached (either because no computer is running the service, or because of a firewall), then it will give the following error message when trying to browse My Network Places:
> *MShome is not accessible. You might not have permission to use this network resource. Contact the administrator of this server to find out if you have access permissions.*   
>   
>  More Info [MS KB318030](http://support.microsoft.com/kb/318030 "You cannot access shared files and folders or browse computers in the workgroup [Q318030]")  
>  More Info [MS KB913619](http://support.microsoft.com/kb/913619 "Error message in Windows XP: "MShome is not accessible" [Q913619]")

 More Info [Microsoft Technet](http://www.microsoft.com/technet/prodtechnol/windows2000serv/reskit/tcpip/part4/tcpappi.asp "Appendix I - Windows 2000 Browser Service")  
 More Info [MS KB188001](http://support.microsoft.com/kb/188001 "Description of the Microsoft Computer Browser Service [Q188001]")  
 More Info [MS KB188305](http://support.microsoft.com/kb/188305 "Troubleshooting the Microsoft Computer Browser Service [Q188305]")  
 More Info [MS KB262694](http://support.microsoft.com/kb/262694 "MS00-036: Malicious User Can Shut Down Computer Browser Service [Q262694]")  
 More Info [MS KB875362](http://support.microsoft.com/kb/875362 "The Computer Browser service does not start and event ID 7024 is logged when you restart your Windows XP Service Pack 2-based computer [Q875362]")  
  
##### Recommended State:

- Automatic, if on a network and there is no dedicated master browser.
- Disabled, if not using network shares or shared printers on the network.

##### Default State:

- Win8: Manual (Trigger Start - FIREWALL PORT EVENT)
- Win7: Manual
- Vista: Automatic (Not Started)
- WinXP/Win2k/WinNT4: Automatic

##### Process Name:

- Win8/Win7/Vista: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Browser)
- WinXP/2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Browser)
- Win2k: [services.exe](/article/winnt-services-wrapper.html) (Browser)

##### Supports:

- None

##### Depends:

- [Server](/article/winnt-services-lanmanserver.html)
- [Workstation](/article/winnt-services-lanmanworkstation.html)
- [TCP/IP NetBIOS Helper Service](/article/winnt-services-lmhosts.html) (WinNT4 only)