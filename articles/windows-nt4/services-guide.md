---
title: Windows NT4 Services Guide
date: '2006-11-14T23:28:05+01:00'
status: publish
permalink: /articles/windows-nt4/services/
author: Snakefoot
excerpt: ''
type: page
id: 3
description:
    - 'How to tweak the services in Windows NT4, with description of what services are unnecessary and can be disabled for security and performance.'
tags:
    - ''
---

##### Windows NT4 Services Guide

To access the service configuration:

-   Control Panel -> Services.
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
| [Clipbook](http://smallvoid.com/article/winnt-services-clipsrv.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Computer Browser](http://smallvoid.com/article/winnt-services-browser.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Directory Replicator](http://smallvoid.com/article/winnt-services-ntfrs.html) | Manual | Manual | Manual |
| [Event Log](http://smallvoid.com/article/winnt-services-eventlog.html) | Automatic | Automatic | Automatic |
| [Fax Service](http://smallvoid.com/article/winnt-services-fax.html) | Manual | Manual | Manual |
| [License Logging Service](http://smallvoid.com/article/winnt-services-licenseservice.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Messenger](http://smallvoid.com/article/winnt-services-messenger.html) | Automatic | Disabled *(Lock) | Disabled *(Lock) |
| [NET Logon](http://smallvoid.com/article/winnt-services-netlogon.html) | Manual | Manual | Manual |
| [Network DDE](http://smallvoid.com/article/winnt-services-netdde.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Network DDE DSDM](http://smallvoid.com/article/winnt-services-netddedsdm.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [NT LM Security Support Provider](http://smallvoid.com/article/winnt-services-ntlmssp.html) | Manual | Manual | Manual |
| [Plug and Play](http://smallvoid.com/article/winnt-services-plugplay.html) | Automatic | Automatic | Automatic |
| [Protected Storage](http://smallvoid.com/article/winnt-services-protectedstorage.html) | Automatic | Automatic | Automatic |
| [Remote Procedure Call (RPC)](http://smallvoid.com/article/winnt-services-rpcss.html) | Automatic | Automatic | Automatic |
| [Remote Procedure Call (RPC) Locator](http://smallvoid.com/article/winnt-services-rpclocator.html) | Manual | Manual | Manual |
| [Server](http://smallvoid.com/article/winnt-services-lanmanserver.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Spooler](http://smallvoid.com/article/winnt-services-spooler.html) | Automatic | Automatic | Disabled *(Trim) |
| [System Event Notification](http://smallvoid.com/article/winnt-services-sens.html) | Automatic | Automatic | Automatic |
| [Schedule](http://smallvoid.com/article/winnt-services-schedule.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [TCP/IP NetBIOS Helper Service](http://smallvoid.com/article/winnt-services-lmhosts.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Telephony](http://smallvoid.com/article/winnt-services-tapisrv.html) | Manual | Manual (DUN) | Disabled *(Trim) |
| [Uninterruptible Power Supply](http://smallvoid.com/article/winnt-services-ups.html) | Manual | Manual | Manual |
| [Windows Time](http://smallvoid.com/article/winnt-services-w32time.html) | Manual | Disabled *(Trim) | Disabled *(Trim) |
| [Workstation](http://smallvoid.com/article/winnt-services-lanmanworkstation.html) | Automatic | Automatic (Net) | Disabled *(Trim) |

##### Other Service Guides:

-   [ArsTechnica.com : Managing Your NT Services](http://www.arstechnica.com/tweak/nt/ntservices-1.html)