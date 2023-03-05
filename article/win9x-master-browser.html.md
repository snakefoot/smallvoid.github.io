---
title: 'Configure master browser election in Windows 9x'
date: '2002-12-20T22:09:47+01:00'
status: publish
permalink: /article/win9x-master-browser.html
author: Snakefoot
excerpt: 'How to configure whether Windows 95 / 98 / Me should participate in the master browser election.'
type: post
id: 203
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - master-browser
    - microsoft-network
post_format: []
tags:
    - 'master-browser,microsoft-network'
---
When having "File and Print Sharing..." installed then Win9x/Me will try to participate in the master browser election. This behavior is controlled with the following values :

- Enabled : Specifies that this computer will participate with a higher priority in the master browser election, and will start an election at boot.
- Disabled : Specifies that this computer will not participate in the master browser election.
- Automatic : Specifies that if no master browser is found then it will initiate an election and participate with a standard priority.
 
 To configure this value:
1. Right click "Network Neighborhood" and select properties
2. Select the tab "Configuration"
3. Select the service "File and printer sharing for Microsoft Networks"
4. Press the button "Properties"
5. Select the property "Browse Master"
6. Select the wanted value
 
 This can also be done through the registry :
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\VNETSUP\]  
 >  MaintainServerList="0" (Automatic = "2", Enabled = "1", Disabled = "0")  
 >   
 >  \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\VNETSUP \\Ndi \\Params \\MaintainServerList\]  
 >  default="0" (Automatic = "2", Enabled = "1", Disabled = "0")

 Related [Description of Master Browser in the Microsoft Network](/article/windows-master-browser.html)  
  
 More info [MS KB134304](http://support.microsoft.com/kb/134304 "Troubleshooting Browsing with Client for Microsoft Networks [Q134304]")  
 More info [MS KB150794](http://support.microsoft.com/kb/150794 "MaintainServerList Value Location in Windows 95 Resource Kit [Q150794]")  
 More info [MS KB246489](http://support.microsoft.com/kb/246489 "Frequent Browser Elections When Windows 95 and Windows NT 4.0 Configured in Workgroup [Q246489]")  