---
title: 'RunAs Service / Secondary Logon'
date: '2000-07-23T16:02:39+02:00'
status: publish
permalink: /article/winnt-services-seclogon.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Secondary Logon service.'
type: post
id: 588
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - runas
post_format: []
tags:
    - runas
---
##### Description:

 Enables starting processes under alternate credentials.  
  
 It is good idea not to be logged in as a user with too many privileges, like the administrator account. Since all programs (Also malicious) will automatically be launched with the user's privileges.  
  
 With this service it is possible to still be running administrative tasks, while logged in as a standard user.  
  
 To activate the "Run As..." feature hold down shift while right clicking a shortcut or an exe-file. Or change the properties for the shortcut to "Run as different user"  
  
 Related [How to use Run As... from the command line](/article/winnt-secondary-logon-config.html).  
  
##### Recommended State:

- Disabled, if not needing to start applications under another accounts credentials.
- Manual, if once in awhile need to start an application as another user (Like Administrator).
- Automatic, if constantly starting applications as another user, as it will avoid slow application launch.

##### Default State:

- Win8/Win7 - Manual
- Vista/WinXP/Win2k: Automatic

##### Process Name:

- Win8/Win7/Vista/WinXP/Win2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (seclogon)
- Win2k: [services.exe](/article/winnt-services-wrapper.html) (seclogon)

##### Supports:

- None

##### Depends:

- None