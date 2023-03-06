---
title: 'Windows XP Home cannot join domain, but can access shares'
date: '2007-10-05T00:13:25+02:00'
status: publish
permalink: /article/winnt-home-domain-share.html
author: Snakefoot
excerpt: 'By changing the workgroup of Windows XP Home, then it is possible to get access to domain shares.'
type: post
id: 749
category:
    - 'File Sharing'
tag:
    - crippled
    - microsoft-network
    - windows-domain
post_format: []
tags:
    - 'crippled,windows-domain,microsoft-network'
---
Windows XP Home has been crippled by Microsoft, so it is not capable of joining a Windows Server domain. But one can still access domain shares even if not part of the domain (Like one always has been able to with the [net use](/article/winnt-ipc-share.html#net_use) command).  
  
 If one configures the workgroup of WinXP Home to have the same name as the domain, then one can access domain shares like XP Home was part of the domain:

1. Make sure the user on XP Home has a matching user in the Windows Domain (Same username and password).
2. Open **Control Panel** and double-click the **System**-icon.
3. Select the **Computer Name**-tab and click the **Change...**-button.
4. Change the Workgroup name to the name of the Windows-domain (Not the domain-server name).
5. **My Network Places** should now contain the shares available in the domain, and it is possible to map a network drive to a share within the Windows domain.
 
 Note one can also access shares and printers without needing to change workgroup. When doing a **Map Network Drive...**, then make sure to include the domain-name when specifying the remote share, and the user must be specified as "username@domain-name".
 > \\\\server-name.domain-name\\c$

 Note even if XP Home can access shares on the Windows domain, then it doesn't become member of the domain along with the benefits of [group policies](/article/winnt-group-policy-registry.html) and central user management. If the domain password policy causes the password to expire, then it is not possible to change the password from XP Home.  
  
 Related [Advanced User Management in Windows XP Home](/article/winxp-home-usermgt.html)  
 Related [Enable security tab to change folder permissions in XP Home](/article/winnt-security-configuration-manager.html)  
  
 Credits [WindowsNetworking.com](http://www.windowsnetworking.com/)