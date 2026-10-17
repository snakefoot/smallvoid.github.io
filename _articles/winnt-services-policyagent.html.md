---
title: 'IPSEC Policy Agent'
date: '2000-07-23T02:30:42+02:00'
permalink: /article/winnt-services-policyagent.html
author: Snakefoot
excerpt: 'Description and recommended settings for the IPSEC services.'
type: post
id: 555
categories:
    - windows-2000_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
    - windows-8-win8_services-guide
tags:
    - firewall
    - ipsec
    - l2tp
    - VPN
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

 More Info <a href="https://www.bing.com/search?q=KB%20231585%20Q231585" rel="nofollow" title="Overview of Secure IP Communication with IPSec in Windows 2000 [Q231585]">MS KB231585</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20234580%20Q234580" rel="nofollow" title="'Soft Associations' Between IPSec-Enabled and Non-IPSec-Enabled Computers [Q234580]">MS KB234580</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20240262%20Q240262" rel="nofollow" title="How to Configure a L2TP/IPSec Connection Using Pre-shared Key Authentication [Q240262]">MS KB240262</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20247231%20Q247231" rel="nofollow" title="Event ID 20111, Error 792 or Error 781 When Establishing an L2TP/IPSec Connection [Q247231]">MS KB247231</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20248750%20Q248750" rel="nofollow" title="Description of the IPSec Policy Created for L2TP/IPSec [Q248750]">MS KB248750</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20252735%20Q252735" rel="nofollow" title="How to Configure IPSec Tunneling in Windows 2000 [Q252735]">MS KB252735</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20253169%20Q253169" rel="nofollow" title="Traffic That Can--and Cannot--Be Secured by IPSec [Q253169]">MS KB253169</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20257225%20Q257225" rel="nofollow" title="Basic IPSec Troubleshooting in Windows 2000 [Q257225]">MS KB257225</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20259335%20Q259335" rel="nofollow" title="Basic L2TP/IPSec Troubleshooting in Windows [Q259335]">MS KB259335</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20265112%20Q265112" rel="nofollow" title="IPSec and L2TP Implementation in Windows 2000 [Q265112]">MS KB265112</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20314831%20Q314831" rel="nofollow" title="Basic L2TP/IPSec Troubleshooting in Windows XP [Q314831]">MS KB314831</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20810207%20Q810207" rel="nofollow" title="IPSec Default Exemptions Are Removed in Windows Server 2003 [Q810207]">MS KB810207</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20811832%20Q811832" rel="nofollow" title="IPSec Default Exemptions Can Be Used to Bypass IPsec Protection in Some Scenarios [Q811832]">MS KB811832</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20813878%20Q813878" rel="nofollow" title="How to Block Specific Network Protocols and Ports by Using IPSec [Q813878]">MS KB813878</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20816514%20Q816514" rel="nofollow" title="HOW TO: Configure IPSec Tunneling in Windows Server 2003 [Q816514]">MS KB816514</a>  
  
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