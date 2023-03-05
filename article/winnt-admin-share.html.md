---
title: 'Prevent the creation of the administrator shares'
date: '2002-04-01T23:06:02+02:00'
status: publish
permalink: /article/winnt-admin-share.html
author: Snakefoot
excerpt: 'Windows creates by default a network shares for each drive letter, which is used for administrative tasks.'
type: post
id: 438
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - network-share
post_format: []
tags:
    - network-share
---
By default the drive letters are shared (C$, D$, ADMIN$ etc.) as [hidden shares](/article/hidden-file-shares.html) for Administrator access. Even if you delete the shares manually they will be recreated at next bootup.  
  
 To remove these shares for good add the following DWORD registry values:  
  
 NT Server:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  AutoShareServer=0

 NT Workstation:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  AutoShareWks=0

 Note that the [IPC$ share](/article/winnt-ipc-share.html) will not be removed by setting these registry values.  
  
 Note that it will only stop Windows from creating the shares at startup, one have to delete the admin shares one self, but only once after changing the above registry keys. Besides using the standard interface for removing the shares, one can also find and delete the shares by editing the registry database at this location:
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanServer \\Shares\]  
 >   
 >  More Info [MS KB125996](http://support.microsoft.com/kb/125996 "Saving and restoring existing Windows shares [Q125996]")

 Note the administrative shares are required by Microsoft Operations Manager (MOM) and Microsoft Systems Management Server (SMS), and have to be enabled on the client machines for them to function properly.  
  
 More Info [MS KB245117](http://support.microsoft.com/kb/245117 "Administrative Shares Do Not Appear on Server [Q245117]")  
 More Info [MS KB288164](http://support.microsoft.com/kb/288164 "How to Prevent the Creation of Administrative Shares on Windows NT Server 4.0 [Q288164]") (Replaces MS KB318751)  
 More Info [MS KB314984](http://support.microsoft.com/kb/314984 "HOW TO: Create and Delete Hidden or Administrative Shares on Client Computers [Q314984]")  
 More Info [MS KB318755](http://support.microsoft.com/kb/318755 "HOW TO: Restore Administrative Shares That Have Been Deleted [Q318755]")  
 More Info [MS KB816113](http://support.microsoft.com/kb/816113 "How to use Registry Editor to restore administrative shares in Windows Server 2003 [Q816113]")  
 More Info [MS KB816524](http://support.microsoft.com/kb/816524 "How to remove administrative shares in Windows Server 2003 [Q816524]")  
 More Info [MS KB842715](http://support.microsoft.com/kb/842715 "Overview of problems that may occur when administrative shares are missing [Q842715]") (Description of side-effects)  