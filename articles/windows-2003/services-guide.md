---
title: Windows 2000 Services Guide
date: '2006-11-14T23:28:05+01:00'
status: publish
permalink: /articles/windows-2003/services/
author: Snakefoot
excerpt: ''
type: page
id: 3
description:
    - 'How to tweak the services in Windows 2003, with description of what services are unnecessary and can be disabled for security and performance.'
tags:
    - ''
---

##### Windows 2003 Services Guide

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
| [Alerter](http://smallvoid.com/article/winnt-services-alerter.html) | Disabled | Disabled (Lock) | Disabled (Lock) |
| [Application Layer Gateway](http://smallvoid.com/article/winnt-services-alg.html) | Manual | Manual (Care) | Disabled *(Trim) |
| [Application Management](http://smallvoid.com/article/winnt-services-appmgmt.html) | Manual | Manual | Manual |
| [Automatic Updates](http://smallvoid.com/article/winnt-services-wuauserv.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [Background Intelligent Transfer](http://smallvoid.com/article/winnt-services-bits.html) | Manual | Manual (Care) | Disabled *(Trim) |
| [Clipbook](http://smallvoid.com/article/winnt-services-clipsrv.html) | Disabled | Disabled (Lock) | Disabled (Lock) |
| [Computer Browser](http://smallvoid.com/article/winnt-services-browser.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [COM+ Event System](http://smallvoid.com/article/winnt-services-eventsystem.html) | Manual | Manual | Manual |
| [COM+ System Application](http://smallvoid.com/article/winnt-services-comsysapp.html) | Manual | Manual | Manual |
| [Cryptographic Services](http://smallvoid.com/article/winnt-services-cryptsvc.html) | Automatic | Automatic (Care) | Manual *(Trim) |
| [DCOM Server Process Launcher](http://smallvoid.com/article/winnt-services-dcomlaunch.html) | Automatic | Automatic | Automatic |
| [DHCP Client](http://smallvoid.com/article/winnt-services-dhcp.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Distributed File System](http://smallvoid.com/article/winnt-services-dfs.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Distributed Link Tracking Client](http://smallvoid.com/article/winnt-services-trkwks.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Distributed Link Tracking Server](http://smallvoid.com/article/winnt-services-trksrv.html) | Disabled | Disabled (Trim) | Disabled (Trim) |
| [Distributed Transaction Coordinator](http://smallvoid.com/article/winnt-services-msdtc.html) | Manual | Manual | Manual |
| [DNS Client](http://smallvoid.com/article/winnt-services-dnscache.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Error Reporting Service](http://smallvoid.com/article/winnt-services-ersvc.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Event Log](http://smallvoid.com/article/winnt-services-eventlog.html) | Automatic | Automatic | Automatic |
| [Fax Service](http://smallvoid.com/article/winnt-services-fax.html) | Manual | Manual | Manual |
| [File Replication](http://smallvoid.com/article/winnt-services-ntfrs.html) | Manual | Manual | Manual |
| [Help and Support](http://smallvoid.com/article/winnt-services-helpsvc.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [HTTP SSL](http://smallvoid.com/article/winnt-services-httpfilter.html) | Manual | Manual | Manual |
| [Human Interface Device Access](http://smallvoid.com/article/winnt-services-hidserv.html) | Disabled | Disabled | Disabled |
| [IMAPI CD-Burning COM Service](http://smallvoid.com/article/winnt-services-imapiservice.html) | Disabled | Disabled | Disabled |
| [Indexing Service](http://smallvoid.com/article/winnt-services-cisvc.html) | Manual | Disabled *(Trim) | Disabled *(Trim) |
| [Intersite Messaging](http://smallvoid.com/article/winnt-services-ismserv.html) | Disabled | Disabled | Disabled |
| [IPSEC Services](http://smallvoid.com/article/winnt-services-policyagent.html) | Automatic | Manual *(Trim) | Manual *(Trim) |
| [Keberos Key Distribution Center](http://smallvoid.com/article/winnt-services-kdc.html) | Disabled | Disabled | Disabled |
| [License Logging Service](http://smallvoid.com/article/winnt-services-licenseservice.html) | Disabled | Disabled | Disabled |
| [Logical Disk Manager](http://smallvoid.com/article/winnt-services-dmserver.html) | Automatic | Automatic | Automatic |
| [Logical Disk Manager Administrative Service](http://smallvoid.com/article/winnt-services-dmadmin.html) | Manual | Manual | Manual |
| [Messenger](http://smallvoid.com/article/winnt-services-messenger.html) | Disabled | Disabled (Lock) | Disabled (Lock) |
| [MS Software Shadow Copy Provider](http://smallvoid.com/article/winnt-services-swprv.html) | Manual | Manual | Manual |
| [NET Logon](http://smallvoid.com/article/winnt-services-netlogon.html) | Manual | Manual | Manual |
| [Netmeeting Remote Desktop Sharing](http://smallvoid.com/article/winnt-services-mnmsrvc.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Network Connections](http://smallvoid.com/article/winnt-services-netman.html) | Manual | Manual | Manual |
| [Network DDE](http://smallvoid.com/article/winnt-services-netdde.html) | Disabled | Disabled (Lock) | Disabled (Lock) |
| [Network DDE DSDM](http://smallvoid.com/article/winnt-services-netddedsdm.html) | Disabled | Disabled (Lock) | Disabled (Lock) |
| [Network Location Awareness](http://smallvoid.com/article/winnt-services-nla.html) | Manual | Manual | Manual |
| Network Provisioning Service | Unknown | Unknown | Unknown |
| [NT LM Security Support Provider](http://smallvoid.com/article/winnt-services-ntlmssp.html) | Manual | Manual | Manual |
| [Performance Logs and Alerts](http://smallvoid.com/article/winnt-services-sysmonlog.html) | Manual | Manual | Manual |
| [Plug and Play](http://smallvoid.com/article/winnt-services-plugplay.html) | Automatic | Automatic | Automatic |
| [Portable Media Serial Number Service](http://smallvoid.com/article/winnt-services-wmdmpmsp.html) | Manual | Manual | Manual |
| [Print Spooler](http://smallvoid.com/article/winnt-services-spooler.html) | Automatic | Automatic | Disabled *(Trim) |
| [Protected Storage](http://smallvoid.com/article/winnt-services-protectedstorage.html) | Automatic | Automatic | Automatic |
| [Remote Access Auto Connection Manager](http://smallvoid.com/article/winnt-services-rasauto.html) | Manual | Manual (DUN) | Disabled * |
| [Remote Access Connection Manager](http://smallvoid.com/article/winnt-services-rasman.html) | Manual | Manual (DUN) | Disabled * |
| [Remote Administration Service](http://smallvoid.com/article/winnt-services-srvcsurg.html) | Automatic | Disabled *(Lock) | Disabled *(Lock) |
| [Remote Desktop Help Session Manager](http://smallvoid.com/article/winnt-services-rdsessmgr.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Remote Procedure Call (RPC)](http://smallvoid.com/article/winnt-services-rpcss.html) | Automatic | Automatic | Automatic |
| [Remote Procedure Call (RPC) Locator](http://smallvoid.com/article/winnt-services-rpclocator.html) | Manual | Manual | Manual |
| [Remote Registry Service](http://smallvoid.com/article/winnt-services-remoteregistry.html) | Automatic | Disabled *(Lock) | Disabled *(Lock) |
| [Remote Server Manager](http://smallvoid.com/article/winnt-services-appmgr.html) | Automatic | Disabled *(Lock) | Disabled *(Lock) |
| [Resultant Set of Policy Provider](http://smallvoid.com/article/winnt-services-rsopprov.html) | Manual | Manual | Manual |
| [Routing and Remote Access](http://smallvoid.com/article/winnt-services-remoteaccess.html) | Disabled | Disabled (Lock) | Disabled (Lock) |
| [Secondary Logon](http://smallvoid.com/article/winnt-services-seclogon.html) | Automatic | Manual *(Trim) | Manual *(Trim) |
| [Security Accounts Manager](http://smallvoid.com/article/winnt-services-samss.html) | Automatic | Automatic | Automatic |
| [Server](http://smallvoid.com/article/winnt-services-lanmanserver.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Shell Hardware Detection](http://smallvoid.com/article/winnt-services-shellhwdetection.html) | Automatic | Automatic | Disabled *(Trim) |
| [Smart Card](http://smallvoid.com/article/winnt-services-scardsvr.html) | Manual | Manual | Manual |
| [Special Administration Console Helper](http://smallvoid.com/article/winnt-services-sacsvr.html) | Manual | Manual | Manual |
| [System Event Notification](http://smallvoid.com/article/winnt-services-sens.html) | Automatic | Automatic | Automatic |
| [Task Scheduler](http://smallvoid.com/article/winnt-services-schedule.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [TCP/IP NetBIOS Helper Service](http://smallvoid.com/article/winnt-services-lmhosts.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Telephony](http://smallvoid.com/article/winnt-services-tapisrv.html) | Manual | Manual (DUN) | Disabled *(Trim) |
| [Telnet](http://smallvoid.com/article/winnt-services-telnet.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Terminal Services](http://smallvoid.com/article/winnt-services-termservice.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Terminal Services Licensing](http://smallvoid.com/article/winnt-services-termservlicensing.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Terminal Services Session Directory](http://smallvoid.com/article/winnt-services-tssdis.html) | Disabled | Disabled | Disabled |
| [Themes](http://smallvoid.com/article/winnt-services-themes.html) | Disabled | Automatic * | Disabled (Trim) |
| [Uninterruptible Power Supply](http://smallvoid.com/article/winnt-services-ups.html) | Manual | Manual | Manual |
| [Upload Manager](http://smallvoid.com/article/winnt-services-uploadmgr.html) | Manual | Manual | Manual |
| [Virtual Disk Service](http://smallvoid.com/article/winnt-services-vds.html) | Manual | Manual | Manual |
| [Volume Shadow Copy](http://smallvoid.com/article/winnt-services-vss.html) | Manual | Manual | Manual |
| [WebClient](http://smallvoid.com/article/winnt-services-webclient.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Windows Audio](http://smallvoid.com/article/winnt-services-audiosrv.html) | Automatic | Automatic | Automatic |
| [Windows Firewall/Internet Connection Sharing (ICS)](http://smallvoid.com/article/winxp-services-sharedaccess.html) | Disabled | Automatic *(Care) | Disabled (Trim) |
| [Windows Image Acquisition (WIA)](http://smallvoid.com/article/winnt-services-stisvc.html) | Disabled | Disabled | Disabled |
| [Windows Installer](http://smallvoid.com/article/winnt-services-msiserver.html) | Manual | Manual | Manual |
| [Windows Management Instrumentation](http://smallvoid.com/article/winnt-services-winmgmt.html) | Automatic | Automatic | Automatic |
| [Windows Management Instrumentation Driver Extentions](http://smallvoid.com/article/winnt-services-wmi.html) | Manual | Manual | Manual |
| [Windows Time](http://smallvoid.com/article/winnt-services-w32time.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [WinHTTP Web Proxy Auto-Discovery Service](http://smallvoid.com/article/winnt-services-winhttpautoproxysvc.html) | Manual | Manual | Manual |
| [Wireless Zero Configuration](http://smallvoid.com/article/winnt-services-wzcsvc.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [WMI Performance Adapter](http://smallvoid.com/article/winnt-services-wmiapsrv.html) | Manual | Manual | Manual |
| [Workstation](http://smallvoid.com/article/winnt-services-lanmanworkstation.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Application Experience](http://smallvoid.com/article/winnt-services-aelookupsvc.html) | Pending | Pending | Pending |
| [Removable Storage Manager (RSM)](http://smallvoid.com/article/winnt-services-ntmssvc.html) | Pending | Pending | Pending |

##### Other Service Guides:

-   [Microsoft : System Services for the Windows Server 2003 Family](http://technet.microsoft.com/en-us/library/cc781474.aspx)
-   [Microsoft : Threats and Countermeasures - System Services](http://www.microsoft.com/technet/security/guidance/serversecurity/tcg/tcgch07n.mspx)
-   [Microsoft : Windows Server 2003 System Services Reference](http://www.microsoft.com/downloads/details.aspx?familyid=b38a0682-2997-4678-9d9e-a07cc66a3bba)
-   [Microsoft : Services that are automatically started in Windows 2003, XP and 2000](http://support.microsoft.com/kb/919520)