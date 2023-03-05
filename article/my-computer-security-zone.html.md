---
title: 'Configure the My Computer security zone'
date: '2002-03-19T22:04:37+01:00'
status: publish
permalink: /article/my-computer-security-zone.html
author: Snakefoot
excerpt: 'Display the My Computer security zone along with the other security zones for configuration.'
type: post
id: 282
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - security-zone
    - windows-explorer
post_format: []
tags:
    - 'security-zone,windows-explorer'
---
Internet Explorer supports several security zones, which allows one to restrict the privileges of the web page being viewed. The security zone used for restricting the web page depends on where the web page is located.

- Internet
- Local Intranet
- Trusted sites
- Restricted sites
- My Computer
 
 The "My Computer" security zone allows by default the web page and the scripts within the web page to have full access to the computer. The "My Computer" security zone is not shown along with the other zones in the Internet Explorer options, but it can be configured to be shown. > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\InternetSettings \\Zones \\0\]  
>  Flags = 1 (Default Decimal = 33)

 Note before making any changes to the "My Computer" security zone, then one should make a backup of the registry settings, as the Internet Explorer is tightly integrated with Windows Explorer.  
  
 More Info [MS KB182569](http://support.microsoft.com/kb/182569 "Description of Internet Explorer Security Zones Registry Entries [Q182569]")  
 More Info [MS KB315933](http://support.microsoft.com/kb/315933 "How to Enable the My Computer Security Zone in Internet Options [Q315933]")  
  
 Related [Configure IE to avoid ActiveX and cookies for unknown sites](/article/ie-restrict-untrusted.html)  
  
 Credits [ibelite.com](http://www.ibelite.com/)  