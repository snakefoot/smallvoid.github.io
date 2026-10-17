---
title: 'Prevent the creation of the administrator shares'
date: '2002-04-01T23:06:02+02:00'
permalink: /article/winnt-admin-share.html
author: Snakefoot
excerpt: 'Windows creates by default a network shares for each drive letter, which is used for administrative tasks.'
type: post
id: 438
categories:
    - windows-2003_file-sharing
    - windows-nt4_file-sharing
    - windows-xp_file-sharing
    - windows-2000_file-sharing
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
 >  More Info <a href="https://www.bing.com/search?q=KB+125996+Q125996" rel="nofollow" title="Saving and restoring existing Windows shares [Q125996]">MS KB125996</a>

 Note the administrative shares are required by Microsoft Operations Manager (MOM) and Microsoft Systems Management Server (SMS), and have to be enabled on the client machines for them to function properly.  
  
 More Info <a href="https://www.bing.com/search?q=KB+245117+Q245117" rel="nofollow" title="Administrative Shares Do Not Appear on Server [Q245117]">MS KB245117</a>  
 More Info <a href="https://www.bing.com/search?q=KB+288164+Q288164" rel="nofollow" title="How to Prevent the Creation of Administrative Shares on Windows NT Server 4.0 [Q288164]">MS KB288164</a> (Replaces MS KB318751)  
 More Info <a href="https://www.bing.com/search?q=KB+314984+Q314984" rel="nofollow" title="HOW TO: Create and Delete Hidden or Administrative Shares on Client Computers [Q314984]">MS KB314984</a>  
 More Info <a href="https://www.bing.com/search?q=KB+318755+Q318755" rel="nofollow" title="HOW TO: Restore Administrative Shares That Have Been Deleted [Q318755]">MS KB318755</a>  
 More Info <a href="https://www.bing.com/search?q=KB+816113+Q816113" rel="nofollow" title="How to use Registry Editor to restore administrative shares in Windows Server 2003 [Q816113]">MS KB816113</a>  
 More Info <a href="https://www.bing.com/search?q=KB+816524+Q816524" rel="nofollow" title="How to remove administrative shares in Windows Server 2003 [Q816524]">MS KB816524</a>  
 More Info <a href="https://www.bing.com/search?q=KB+842715+Q842715" rel="nofollow" title="Overview of problems that may occur when administrative shares are missing [Q842715]">MS KB842715</a> (Description of side-effects)  