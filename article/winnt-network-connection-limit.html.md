---
title: 'No more than 10 concurrent connections to a remote computer'
date: '2005-10-26T23:03:09+02:00'
status: publish
permalink: /article/winnt-network-connection-limit.html
author: Snakefoot
excerpt: 'Windows Professional / Home edition includes limitation for not handling more than 10 SMB connections.'
type: post
id: 450
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - crippled
    - network-share
post_format: []
tags:
    - 'network-share,crippled'
---
Microsoft have created several limitations in the Workstation, Professional and Home edition of Windows, so they are crippled compared to the server-edition. This is to encourage users to buy the more expensive server license.  
  
 When sharing a file/printer, then there is a limit for how many users that can access the shared resource from the Local Area Network (LAN) simultaneously. The actual inbound SMB connection limit (Prof=10)/(Home=5) can be seen by running this command:

> net config server

 If a user tries to access a network share on a computer where the limit is reached, then it will give this error:
 > *No more connections can be made to this remote computer at this time because there are already as many connections as the computer can accept.*

 If having problems with users reaching the limit and getting the above message, then one can consider the following solutions:
 - [Upgrade to a Windows Server license](/article/winnt-upgrade-server.html). If having upgraded from a Windows NT4 Workstation to a Windows NT4 Server, then update this registry key:
  > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanManServer \\Parameters\]  
  >  Users = 0xffffff  
  >   
  >  More Info [MS KB122925](http://support.microsoft.com/kb/122925 "Upgrading From Workstation to Server Limited to 10 Connections [Q122925]")  
  >  More Info [MS KB179483](http://support.microsoft.com/kb/179483 "Error Msg: No More Connections Can Be Made At This Time [Q179483]")
- Use Linux with Samba (Some external hard disk storage devices include a small linux distribution with Samba installed).
- Use several computers to share the files/printers
- Decrease the timeout period for user connections, to close unused connections faster (Default 15 minutes):
  > net config server /autodisconnect:1  
  >   
  >  More Info [MS KB122920](http://support.microsoft.com/kb/122920 "Inbound Connections Limit in Windows [Q122920]")  
  >  More Info [MS KB138365](http://support.microsoft.com/kb/138365 "How Autodisconnect Works in Windows NT and Windows 2000 [Q138365]")  
  >  More Info [MS KB314882](http://support.microsoft.com/kb/314882 "Inbound Connections Limit in Windows XP [Q314882]")
- [Restrict anonymous access to file and printer shares](/article/winnt-restrict-anonymous.html) (To avoid wasting sessions on anonymous access). More info [MS KB328459](http://support.microsoft.com/kb/328459 "Troubleshooting Server Message Block Inbound Connection Limit in Windows Peer-to-Peer Workgroup [Q328459]")
- Increase the limit of concurrent incoming SMB commands (different from concurrent SMB sessions), so long-term SMB commands (Like the [Change Notification request](/article/winnt-network-notification.html)) will not block for new SMB commands without having reached the max number of inbound SMB sessions.  
    
  Update the following DWORD registry settings to [optimize the network performance](/article/winnt-smb-settings.html) of Windows XP:
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Lanmanserver \\Parameters\]  
  >  MaxMpxCt = 50 (Default = 10 commands)  
  >  MaxWorkItems = 256 (Default = 64)  
  >  Size = 2 (Default = 1)  
  >   
  >  More Info [MS KB926646](http://support.microsoft.com/kb/926646 "You cannot increase the limit concurrent SMB command in the Windows XP Professional Server service") (Hotfix required for these settings)
- Don't use persistent connections like mapped network drives to the remote computer.
- Use a different protocol than Microsoft Network, to share your files (FTP/WebDAV/P2P) 
  - [Mapping WebDAV folder as a network drive letter](/article/winnt-webdav-network-drive.html)
  - [Mapping FTP server as a network drive letter](/article/ftp-map-network-drive.html)
 
 Related [Increase the max limit for concurrent TCP connections](/article/winnt-tcpip-max-limit.html)