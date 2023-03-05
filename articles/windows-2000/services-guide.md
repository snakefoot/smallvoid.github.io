---
title: Windows 2000 Services Guide
date: '2006-11-14T23:28:05+01:00'
status: publish
permalink: /articles/windows-2000/services/
author: Snakefoot
excerpt: ''
type: page
id: 3
description:
    - 'How to tweak the services in Windows 2000, with description of what services are unnecessary and can be disabled for security and performance.'
tags:
    - ''
---

##### Windows 2000 Services Guide

To access the service configuration:

-   Control Panel -> Administrative Tools -> [Services](http://smallvoid.com/article/winnt-services-config.html)-snapin.
-   Using the registry editor [Regedit to change service state](http://smallvoid.com/article/winnt-services-regedit.html).

A service has 3 basic startup states :

-   Disabled : The service will not be loaded (Some programs stops working, won't take memory, and quick boot time)
-   Manual : The service will be loaded on demand (Slow program start, will take memory when needed, and quick boot time)
-   Automatic : The service is loaded at boot time (Fast program start, will take memory, and slow boot time)

Explanation of recommendations:

-   **Recommended:** For users who prefers things safe and easy
-   **Trimmed:** For users who prefers only to have the most necessary started at the expense of manual maintenance and backup

Comments for recommendations (* = Recommendation divert from "default" state):

-   **Lock**: Increases security by disabling vulnerable features.
-   **Trim**: Lessens CPU/RAM usage on the expense of loosing special features.
-   **Care**: Enables Windows Self Maintenance, so it can take better care of it self.
-   **DUN** (Dial Up Networking): Enables Internet access through a dialup connection like Phone-, ISDN-, Cable- modem (internal or external).
-   **Net** (Network): Enables Internet access and filesharing via the network adapter to a hub, switch, router or another machine. The network is a simple one at home, without Domain Controller, Virtual Private Network or Internet Connection Sharing.

Select recommendation:

| Service | Default | Recommended | Trimmed |
| [Alerter](http://smallvoid.com/article/winnt-services-alerter.html) | Automatic | Disabled *(Lock) | Disabled *(Lock) |
| [Application Management](http://smallvoid.com/article/winnt-services-appmgmt.html) | Manual | Manual | Manual |
| [Automatic Updates](http://smallvoid.com/article/winnt-services-wuauserv.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [Background Intelligent Transfer](http://smallvoid.com/article/winnt-services-bits.html) | Manual | Manual (Care) | Disabled *(Trim) |
| [Clipbook](http://smallvoid.com/article/winnt-services-clipsrv.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Computer Browser](http://smallvoid.com/article/winnt-services-browser.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [COM+ Event System](http://smallvoid.com/article/winnt-services-eventsystem.html) | Manual | Manual | Manual |
| [DHCP Client](http://smallvoid.com/article/winnt-services-dhcp.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Distributed File System](http://smallvoid.com/article/winnt-services-dfs.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Distributed Link Tracking Client](http://smallvoid.com/article/winnt-services-trkwks.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Distributed Link Tracking Server](http://smallvoid.com/article/winnt-services-trksrv.html) | Manual | Disabled *(Trim) | Disabled *(Trim) |
| [Distributed Transaction Coordinator](http://smallvoid.com/article/winnt-services-msdtc.html) | Manual | Manual | Manual |
| [DNS Client](http://smallvoid.com/article/winnt-services-dnscache.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Event Log](http://smallvoid.com/article/winnt-services-eventlog.html) | Automatic | Automatic | Automatic |
| [Fax Service](http://smallvoid.com/article/winnt-services-fax.html) | Manual | Manual | Manual |
| [File Replication](http://smallvoid.com/article/winnt-services-ntfrs.html) | Manual | Manual | Manual |
| [Indexing Service](http://smallvoid.com/article/winnt-services-cisvc.html) | Manual | Disabled *(Trim) | Disabled *(Trim) |
| [Internet Connection Sharing](http://smallvoid.com/article/winnt-services-sharedaccess.html) | Manual | Disabled *(Trim) | Disabled *(Trim) |
| [Intersite Messaging](http://smallvoid.com/article/winnt-services-ismserv.html) | Disabled | Disabled | Disabled |
| [IPSEC Policy Agent](http://smallvoid.com/article/winnt-services-policyagent.html) | Automatic | Manual *(Trim) | Manual *(Trim) |
| [Keberos Key Distribution Center](http://smallvoid.com/article/winnt-services-kdc.html) | Disabled | Disabled | Disabled |
| [License Logging Service](http://smallvoid.com/article/winnt-services-licenseservice.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Logical Disk Manager](http://smallvoid.com/article/winnt-services-dmserver.html) | Automatic | Automatic | Automatic |
| [Logical Disk Manager Administrative Service](http://smallvoid.com/article/winnt-services-dmadmin.html) | Manual | Manual | Manual |
| [Messenger](http://smallvoid.com/article/winnt-services-messenger.html) | Automatic | Disabled *(Lock) | Disabled *(Lock) |
| [NET Logon](http://smallvoid.com/article/winnt-services-netlogon.html) | Manual | Manual | Manual |
| [Netmeeting Remote Desktop Sharing](http://smallvoid.com/article/winnt-services-mnmsrvc.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Network Connections](http://smallvoid.com/article/winnt-services-netman.html) | Manual | Manual | Manual |
| [Network DDE](http://smallvoid.com/article/winnt-services-netdde.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Network DDE DSDM](http://smallvoid.com/article/winnt-services-netddedsdm.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [NT LM Security Support Provider](http://smallvoid.com/article/winnt-services-ntlmssp.html) | Manual | Manual | Manual |
| [Performance Logs and Alerts](http://smallvoid.com/article/winnt-services-sysmonlog.html) | Manual | Manual | Manual |
| [Plug and Play](http://smallvoid.com/article/winnt-services-plugplay.html) | Automatic | Automatic | Automatic |
| [Print Spooler](http://smallvoid.com/article/winnt-services-spooler.html) | Automatic | Automatic | Disabled *(Trim) |
| [Protected Storage](http://smallvoid.com/article/winnt-services-protectedstorage.html) | Automatic | Automatic | Automatic |
| [QoS RSVP](http://smallvoid.com/article/winnt-services-rsvp.html) | Manual | Manual | Manual |
| [Remote Access Auto Connection Manager](http://smallvoid.com/article/winnt-services-rasauto.html) | Manual | Manual (DUN) | Disabled * |
| [Remote Access Connection Manager](http://smallvoid.com/article/winnt-services-rasman.html) | Manual | Manual (DUN) | Disabled * |
| [Remote Procedure Call (RPC)](http://smallvoid.com/article/winnt-services-rpcss.html) | Automatic | Automatic | Automatic |
| [Remote Procedure Call (RPC) Locator](http://smallvoid.com/article/winnt-services-rpclocator.html) | Manual | Manual | Manual |
| [Remote Registry Service](http://smallvoid.com/article/winnt-services-remoteregistry.html) | Automatic | Disabled *(Lock) | Disabled *(Lock) |
| [Removable Storage](http://smallvoid.com/article/winnt-services-ntmssvc.html) | Automatic | Manual *(Trim) | Manual *(Trim) |
| [Routing and Remote Access](http://smallvoid.com/article/winnt-services-remoteaccess.html) | Disabled | Disabled | Disabled |
| [RunAs Service](http://smallvoid.com/article/winnt-services-seclogon.html) | Automatic | Manual *(Trim) | Manual *(Trim) |
| [Security Accounts Manager](http://smallvoid.com/article/winnt-services-samss.html) | Automatic | Automatic | Automatic |
| [Server](http://smallvoid.com/article/winnt-services-lanmanserver.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Smart Card](http://smallvoid.com/article/winnt-services-scardsvr.html) | Manual | Manual | Manual |
| [Smart Card Helper](http://smallvoid.com/article/winnt-services-scarddrv.html) | Manual | Manual | Manual |
| [System Event Notification](http://smallvoid.com/article/winnt-services-sens.html) | Automatic | Automatic | Automatic |
| [Task Scheduler](http://smallvoid.com/article/winnt-services-schedule.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [TCP/IP NetBIOS Helper Service](http://smallvoid.com/article/winnt-services-lmhosts.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Telephony](http://smallvoid.com/article/winnt-services-tapisrv.html) | Manual | Manual (DUN) | Disabled *(Trim) |
| [Telnet](http://smallvoid.com/article/winnt-services-telnet.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Terminal Services](http://smallvoid.com/article/winnt-services-termservice.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Terminal Services Licensing](http://smallvoid.com/article/winnt-services-termservlicensing.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Uninterruptible Power Supply](http://smallvoid.com/article/winnt-services-ups.html) | Manual | Manual | Manual |
| [Utility Manager](http://smallvoid.com/article/winnt-services-utilman.html) | Manual | Manual | Manual |
| [Windows Installer](http://smallvoid.com/article/winnt-services-msiserver.html) | Manual | Manual | Manual |
| [Windows Management Instrumentation](http://smallvoid.com/article/winnt-services-winmgmt.html) | Automatic | Automatic | Automatic |
| [Windows Management Instrumentation Driver Extentions](http://smallvoid.com/article/winnt-services-wmi.html) | Manual | Manual | Manual |
| [Windows Time](http://smallvoid.com/article/winnt-services-w32time.html) | Manual | Disabled *(Trim) | Disabled *(Trim) |
| [Wireless Configuration](http://smallvoid.com/article/winnt-services-wzcsvc.html) | Manual | Manual (Net) | Disabled *(Trim) |
| [WMDM PMSP Service](http://smallvoid.com/article/winnt-services-wmdmpmsp.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Workstation](http://smallvoid.com/article/winnt-services-lanmanworkstation.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Human Interface Device Access / HID Input Service](http://smallvoid.com/article/winnt-services-hidserv.html) | Pending | Pending | Pending |

##### Other Service Guides:

-   [Microsoft : Glossary of Windows 2000 Services](http://www.microsoft.com/windows2000/techinfo/howitworks/management/w2kservices.asp)
-   [Microsoft : Purpose of Windows 2000 Services](http://www.microsoft.com/technet/security/prodtech/windows2000/secwin2k/swin2kaa.mspx)
-   [3DSpotlight : Windows 2000 Services tweak guide](http://www.3dspotlight.com/tweaks/win2k_services/index.shtml)
-   [WindowsNetworking.com : Disable unnecessary services to improve workstations performance](http://www.wown.com/kbase/WindowsTips/WindowsXP/UserTips/Performance/Disableunnecessaryservicestoimproveworkstationsperformance.html)
-   [Black Viper's Windows 2000 Professional Services Configurations](http://www.blackviper.com/WIN2K/servicecfg.htm) - [Mirror](http://web.archive.org/web/20050401024021/http://www.blackviper.com/WIN2K/servicecfg.htm)
-   [Tweak3d.net : Windows 2000 Hard Drive and Memory Tweak Guide](http://www.tweak3d.net/tweak/win2kmem/6.shtml)