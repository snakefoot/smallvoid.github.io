---
title: 'Restrict access for NULL sessions'
date: '2002-02-06T13:30:43+01:00'
permalink: /article/winnt-restrict-anonymous.html
author: Snakefoot
excerpt: 'How to prevent access for anonymous to see available shares and user accounts.'
type: post
id: 145
categories:
    - windows-2003_user-security
    - windows-nt4_user-security
    - windows-xp_user-security
    - windows-2000_user-security
tags:
    - anonymous-access
    - guest-account
    - null-session
    - user-account
---
By standard it is possible for anonymous users to use NULL sessions to view:

- Minimum Password length
- If blank passwords are permitted
- Maximum password age
- Password history
- Userlist
- Network shares
 
 This can be restricted by changing this DWORD in the registry:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\LSA\]  
>  RestrictAnonymous = 2 (Default = 0)  
>   
>  0 = None. Rely on default permissions  
>  1 = Do not allow enumeration of SAM accounts and names (Will stop NULL session exploits)  
>  2 = No access without explicit anonymous permissions (Win2k only)  
>   
>  Note if enabling this restriction it will disable guest account users from seeing Network Shares, as they will fail login with security error code : 3221225572 (Logon Failed : The username doesn't exist)  
>   
>  More info <a href="https://www.bing.com/search?q=KB+143474+Q143474" rel="nofollow" title="Restricting Information Available to Anonymous Logon Users [Q143474]">MS KB143474</a>  
>  More info <a href="https://www.bing.com/search?q=KB+246261+Q246261" rel="nofollow" title="How to Use the RestrictAnonymous Registry Value in Windows 2000 [Q246261]">MS KB246261</a>  
>  More info <a href="https://www.bing.com/search?q=KB+296405+Q296405" rel="nofollow" title="The 'RestrictAnonymous' Registry Value May Break the Trust to a Windows 2000 Domain [Q296405]">MS KB296405</a>  
>  More info <a href="https://www.bing.com/search?q=KB+328459+Q328459" rel="nofollow" title="Troubleshooting Server Message Block Inbound Connection Limit in Windows Peer-to-Peer Workgroup [Q328459]">MS KB328459</a>  
>  More info <a href="https://www.bing.com/search?q=KB+837964+Q837964" rel="nofollow" title="Security issues with LDAP NULL base connections [Q837964]">MS KB837964</a>

 It is also possible to access shares using NULL sessions. For security reasons it is only possible for a set of restricted shares (Besides [IPC$](/article/winnt-ipc-share.html)) specified here:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  NullSessionPipes = "..."  
>  NullSessionShares = "..."  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  RestrictNullSessAccess = 1 (Secure = 1, Unsecure = 0, Default = No Value; Secure)  
>   
>  More info <a href="https://www.bing.com/search?q=KB+122702+Q122702" rel="nofollow" title="Using the System Account as a Service in Windows NT 3.5 [Q122702]">MS KB122702</a>  
>  More info <a href="https://www.bing.com/search?q=KB+289655+Q289655" rel="nofollow" title="HOW TO: Enable Null Session Shares on a Windows 2000-Based Computer [Q289655]">MS KB289655</a>  
>  More info <a href="https://www.bing.com/search?q=KB+815458+Q815458" rel="nofollow" title="You Can Use the Llsrpc Named Pipe to Add or Delete Licenses and Create New License Groups [Q815458]">MS KB815458</a>  
>  More info <a href="https://www.bing.com/search?q=KB+830070+Q830070" rel="nofollow" title="Anonymous access by using a null session is possible after you configure the registry to restrict remote access [Q830070]">MS KB830070</a>  
>  More info <a href="https://www.bing.com/search?q=KB+896658+Q896658" rel="nofollow" title="Windows 2000 Service Pack 4 does not update the Netserv.inf file when creating a slipstream installation [Q896658]">MS KB896658</a>

 Windows XP/2003 introduced a new setting "Network Access: Do not allow anonymous enumeration of SAM accounts", which disables enumerations of SAM accounts, but still allows enumerations of shares (For Simple File Sharing): 
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\LSA\]  
>  RestrictAnonymousSAM = 1 (Default = 1)  
>   
>  More info <a href="https://www.bing.com/search?q=KB+328459+Q328459" rel="nofollow" title="Troubleshooting Server Message Block Inbound Connection Limit in Windows Peer-to-Peer Workgroup [Q328459]">MS KB328459</a>

 Windows XP/2003 introduced a new setting "Network access: Let Everyone permissions apply to anonymous users", which enforces that all rights given to the Everyone-group (authenticated users) are not automatically given to the Anonymous Logon security group. Before Windows XP the Everyone-group included both authenticated users and anonymous users:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\LSA\]  
>  EveryoneIncludesAnonymous = 0 (Default = 0)  
>   
>  More info <a href="https://www.bing.com/search?q=KB+278259+Q278259" rel="nofollow" title="Everyone Group Does Not Include Anonymous Security Identifier [Q278259]">MS KB278259</a>

 Related [Using NULL sessions to access this information](/article/winnt-null-session.html)  
  
 More info <a href="https://www.bing.com/search?q=KB+823659+Q823659" rel="nofollow" title="Client, service, and program incompatibilities that may occur when you modify security settings and user rights assignments [Q823659]">MS KB823659</a>  
 More info <a href="https://www.bing.com/search?q=KB+889030+Q889030" rel="nofollow" title="Trust between a Windows NT domain and an Active Directory domain cannot be established or it does not work as expected [Q889030]">MS KB889030</a>  