---
title: 'Remote Procedure Call (RPC)'
date: '2000-06-06T16:43:14+02:00'
permalink: /article/winnt-services-rpcss.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Procedure Call service.'
type: post
id: 581
categories:
    - windows-2000_services
    - windows-nt4_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
    - windows-8-win8_services-guide
tags:
    - remote-procedure-call
---
##### Description:

 The service provides the endpoint mapper and other miscellaneous RPC services.  
  
 Remote Procedure Call (RPC) is a protocol used by the Windows operating system. RPC provides an inter-process communication mechanism that allows a program running on one computer to seamlessly execute code on a remote system. The protocol itself is derived from the Open Software Foundation (OSF) RPC protocol, but with the addition of some Microsoft specific extensions. By default this service accepts connections at TCP port 135.  
  
 Note if by accident having configured the service to be Disabled, then one have to <a href="https://www.bing.com/search?q=KB+315222+Q315222" title="A description of the Safe Mode Boot options in Windows XP [Q315222]" rel="nofollow">boot in safemode</a> and and set the service to Automatic. If the [service applet](/article/winnt-services-config.html) doesn't work one can either do it through the [registry](/article/winnt-services-regedit.html) or with [Msconfig](/article/win2k-msconfig.html)  
  
 Note to configure the behavior and access to this service run this command:
> DcomCnfg.exe  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20825750%20Q825750" rel="nofollow" title="How to disable DCOM support in Windows [Q825750]">MS KB825750</a>

 Note when the RPC service fails to contact a remote computer / server / domain (ex. not able to resolve DNS name, not able to ping IP address, not having a [working TCPIP stack](/article/winnt-netsh.html), not having the proper trust relations, all resources on the remote computer are used up), then one might get the following error:
> *The RPC Server is Unavailable  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20224370%20Q224370" rel="nofollow" title="Troubleshooting 'RPC Server is Unavailable' in Windows [Q224370]">MS KB224370</a>*

 More Info <a href="https://www.bing.com/search?q=KB%20154596%20Q154596" rel="nofollow" title="HOWTO: Configure RPC Dynamic Port Allocation to Work with Firewall [Q154596]">MS KB154596</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20171307%20Q171307" rel="nofollow" title="How to Disable SAP Broadcast for RPC Service [Q171307]">MS KB171307</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20229702%20Q229702" rel="nofollow" title="Unable to Prevent RPC from Binding to an Interface [Q229702]">MS KB229702</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20825819%20Q825819" rel="nofollow" title="How to Remove COM Internet Services (CIS) and RPC over HTTP Proxy Support [Q825819]">MS KB825819</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20826382%20Q826382" rel="nofollow" title="How to Disable DCOM Support in RPC over HTTP [Q826382]">MS KB826382</a>  
  
 Related [Blaster RPC Exploit](/article/winnt-blaster-rpc-exploit.html)  
  
##### Recommended State:

- Automatic, vital part

##### Default State:

- Automatic

##### Process Name:

- WinNT4: Rpcss.exe
- Win2k/WinXP/Win2k3/Vista: [svchost -k rpcss](/article/winnt-services-wrapper.html) (RpcSs)

##### Supports:

- Everything

##### Depends:

- [DCOM Server Process Launcher](/article/winnt-services-dcomlaunch.html) (Vista+)
- [RPC Endpoint mapper](/article/winnt-services-rpceptmapper.html) (Win7+)