---
title: 'IPSEC Policy Agent'
date: '2000-07-23T02:30:42+02:00'
status: publish
permalink: /article/winnt-services-policyagent.html
author: Snakefoot
excerpt: 'Description and recommended settings for the IPSEC services.'
type: post
id: 555
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - firewall
    - ipsec
    - l2tp
    - VPN
post_format: []
tags:
    - 'ipsec,VPN,l2tp,firewall'
---
##### Description:

 Manages the Internet Protocol Security (IPSec) policy &amp; starts the Internet Security Association Key Management Protocol (ISAKMP) / Oakley Internet Key Exchange (IKE) &amp; the IP security driver.  
  
 The IP Security driver captures/examines IP traffic and uses the IPSec policies to decide whether to block/filter, permit or encrypt (F.ex. Layer Two Tunneling Protocol - L2TP) the traffic. When changing a policy the IPSec Policy Agent is responsible for updating the IP Security Driver. The service listens on UDP port 500 (ISAKMP) and UDP port 4500 (NAT-T).  
  
 The IP Security driver can be used with the [Remote Access Connection Manager (Rasman)](/article/winnt-services-rasman.html), to provide secure VPN connections.  
  
 Note in Win2k if not having installed "Client for Microsoft Networks" for the Network Adapter (Don't need to be bound), then the service will not start and instead give the following error without any entries in the Event Log:
> *Could not start the IPSEC Policy Agent service on Local Computer.  
>  The service did not return an error. This could be an internal Windows error or an internal service error. If the problem persists, contact your system administrator.*

 Note if IPSec Policies are corrupted (Reload from .ipsec file), or a 3rd Party IPSec/VPN software is installed (Uninstall it), then it might give the following error in the Event Log:
> *IPSEC PolicyAgent Service couldn't be started: Driver failed to start.  
>  Source: PolicyAgent  
>  EventID: 321  
>   
>  IPSEC PolicyAgent Service couldn't be started: Oakley failed to start.  
>  Source: PolicyAgent  
>  EventID: 319*

 More Info [MS KB231585](http://support.microsoft.com/kb/231585 "Overview of Secure IP Communication with IPSec in Windows 2000 [Q231585]")  
 More Info [MS KB234580](http://support.microsoft.com/kb/234580 ""Soft Associations" Between IPSec-Enabled and Non-IPSec-Enabled Computers [Q234580]")  
 More Info [MS KB240262](http://support.microsoft.com/kb/240262 "How to Configure a L2TP/IPSec Connection Using Pre-shared Key Authentication [Q240262]")  
 More Info [MS KB247231](http://support.microsoft.com/kb/247231 "Event ID 20111, Error 792 or Error 781 When Establishing an L2TP/IPSec Connection [Q247231]")  
 More Info [MS KB248750](http://support.microsoft.com/kb/248750 "Description of the IPSec Policy Created for L2TP/IPSec [Q248750]")  
 More Info [MS KB252735](http://support.microsoft.com/kb/252735 "How to Configure IPSec Tunneling in Windows 2000 [Q252735]")  
 More Info [MS KB253169](http://support.microsoft.com/kb/253169 "Traffic That Can--and Cannot--Be Secured by IPSec [Q253169]")  
 More Info [MS KB257225](http://support.microsoft.com/kb/257225 "Basic IPSec Troubleshooting in Windows 2000 [Q257225]")  
 More Info [MS KB259335](http://support.microsoft.com/kb/259335 "Basic L2TP/IPSec Troubleshooting in Windows [Q259335]")  
 More Info [MS KB265112](http://support.microsoft.com/kb/265112 "IPSec and L2TP Implementation in Windows 2000 [Q265112]")  
 More Info [MS KB314831](http://support.microsoft.com/kb/314831 "Basic L2TP/IPSec Troubleshooting in Windows XP [Q314831]")  
 More Info [MS KB810207](http://support.microsoft.com/kb/810207 "IPSec Default Exemptions Are Removed in Windows Server 2003 [Q810207]")  
 More Info [MS KB811832](http://support.microsoft.com/kb/811832 "IPSec Default Exemptions Can Be Used to Bypass IPsec Protection in Some Scenarios [Q811832]")  
 More Info [MS KB813878](http://support.microsoft.com/kb/813878 "How to Block Specific Network Protocols and Ports by Using IPSec [Q813878]")  
 More Info [MS KB816514](http://support.microsoft.com/kb/816514 "HOW TO: Configure IPSec Tunneling in Windows Server 2003 [Q816514]")  
  
##### Recommended State:

- Disabled, if on a simple home network.
- Automatic, if connected to a Windows domain..

##### Default State:

- Win8: Manual (Trigger Start - FIREWALL PORT EVENT).
- Win7: Manual.
- Vista: Automatic.
- Win2k3: Automatic.
- WinXP: Manual.
- Win2k: Automatic.

##### Process Name:

- Win8/Win7/Vista: [svchost.exe -k NetworkServiceNetworkRestricted](/article/winnt-services-wrapper.html) (PolicyAgent)
- WinXP/Win2k3/Win2k: [lsass.exe](/article/winnt-services-wrapper.html) (PolicyAgent)

##### Supports:

- None

##### Depends:

- [Base Filtering Engine](/article/winnt-services-bfe.html) (Vista+)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)