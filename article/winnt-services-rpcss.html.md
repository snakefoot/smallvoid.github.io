---
title: 'Remote Procedure Call (RPC)'
date: '2000-06-06T16:43:14+02:00'
status: publish
permalink: /article/winnt-services-rpcss.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Procedure Call service.'
type: post
id: 581
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - remote-procedure-call
post_format: []
tags:
    - remote-procedure-call
---
##### Description:

 The service provides the endpoint mapper and other miscellaneous RPC services.  
  
 Remote Procedure Call (RPC) is a protocol used by the Windows operating system. RPC provides an inter-process communication mechanism that allows a program running on one computer to seamlessly execute code on a remote system. The protocol itself is derived from the Open Software Foundation (OSF) RPC protocol, but with the addition of some Microsoft specific extensions. By default this service accepts connections at TCP port 135.  
  
 Note if by accident having configured the service to be Disabled, then one have to [boot in safemode](http://support.microsoft.com/kb/315222 "A description of the Safe Mode Boot options in Windows XP [Q315222]") and and set the service to Automatic. If the [service applet](/article/winnt-services-config.html) doesn't work one can either do it through the [registry](/article/winnt-services-regedit.html) or with [Msconfig](/article/win2k-msconfig.html)  
  
 Note to configure the behavior and access to this service run this command:
> DcomCnfg.exe  
>   
>  More Info [MS KB825750](http://support.microsoft.com/kb/825750 "How to disable DCOM support in Windows [Q825750]")

 Note when the RPC service fails to contact a remote computer / server / domain (ex. not able to resolve DNS name, not able to ping IP address, not having a [working TCPIP stack](/article/winnt-netsh.html), not having the proper trust relations, all resources on the remote computer are used up), then one might get the following error:
> *The RPC Server is Unavailable  
>   
>  More Info [MS KB224370](http://support.microsoft.com/kb/224370 "Troubleshooting "RPC Server is Unavailable" in Windows [Q224370]")*

 More Info [MS KB154596](http://support.microsoft.com/kb/154596 "HOWTO: Configure RPC Dynamic Port Allocation to Work with Firewall [Q154596]")  
 More Info [MS KB171307](http://support.microsoft.com/kb/171307 "How to Disable SAP Broadcast for RPC Service [Q171307]")  
 More Info [MS KB229702](http://support.microsoft.com/kb/229702 "Unable to Prevent RPC from Binding to an Interface [Q229702]")  
 More Info [MS KB825819](http://support.microsoft.com/kb/825819 "How to Remove COM Internet Services (CIS) and RPC over HTTP Proxy Support [Q825819]")  
 More Info [MS KB826382](http://support.microsoft.com/kb/826382 "How to Disable DCOM Support in RPC over HTTP [Q826382]")  
  
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