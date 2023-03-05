---
title: 'DCOM Server Process Launcher'
date: '2004-09-12T00:32:56+02:00'
status: publish
permalink: /article/winnt-services-dcomlaunch.html
author: Snakefoot
excerpt: 'Description and recommended settings for the DCOM Server Process Launcher service.'
type: post
id: 533
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 The RPC and DCOM features have been split into two services. This one handles all local requests and runs with Local System privileges. [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) handles remote requests and runs with limited Network Service privilege. If an [attacker](/article/winnt-blaster-rpc-exploit.html) compromises the [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html), then it will only have limited access to the machine.  
  
 Note the following things will fail if this service is not running:
- The builtin [defrag will fail to work](/article/winnt-defrag-repair.html), and if running [Defrag.exe](/article/winnt-defrag-switches.html) from the command line one gets this error:
  > *Windows cannot connect to the Disk Defragmenter engine*
- System Information (MsInfo32) will fail to work and give this error:
  > *Can't Collect Information  
  >  A network error occurred in connecting to Windows Management Instrumentation. Ensure that your network connection is functioning properly.*
- If [Windows Firewall](/article/winnt-services-sharedaccess.html) is enabled, then it will fail to start and all incomming traffic will be blocked. More Info [MS KB892199](http://support.microsoft.com/kb/892199 "The Windows Firewall service in Windows XP Service Pack 2, in Windows XP Professional x64 Edition, in Windows Server 2003 SP1, and in x64-based versions of Windows Server 2003 cannot start if the DCOM Process Launcher Service is disabled [Q892199]")
- Disk Management will fail and give this error:
  > *The RPC server is unavailable*
- Media Player 10 will fail to burn and sync and give this error:
  > *The RPC server is unavailable*
- The install of new applications will fail and give this error:
  > *The InstallShield Engine (iKernel.exe) could not be launched.  
  >  The RPC server is unavailable.*

##### Recommended State:

- Automatic

##### Default State:

- Win8/Win7/Vista: Automatic
- WinXP SP2: Automatic
- Win2k3 SP1: Automatic

##### Process Name:

- [svchost.exe -k DcomLaunch](/article/winnt-services-wrapper.html) (DcomLaunch)

##### Supports:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) (Vista+)
- [Load Session Manager](/article/winnt-services-lsm.html) (Win8+)
- [Background Task Infrastructure Service](/article/winnt-services-brokerinfrastructure.html) (Win8+)

##### Depends:

- None