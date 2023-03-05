---
title: 'Restrict access for NULL sessions'
date: '2002-02-06T13:30:43+01:00'
status: publish
permalink: /article/winnt-restrict-anonymous.html
author: Snakefoot
excerpt: 'How to prevent access for anonymous to see available shares and user accounts.'
type: post
id: 145
category:
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - anonymous-access
    - guest-account
    - null-session
    - user-account
post_format: []
tags:
    - 'null-session,anonymous-access,guest-account,user-account'
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
>  More info [MS KB143474](http://support.microsoft.com/kb/143474 "Restricting Information Available to Anonymous Logon Users [Q143474]")  
>  More info [MS KB246261](http://support.microsoft.com/kb/246261 "How to Use the RestrictAnonymous Registry Value in Windows 2000 [Q246261]")  
>  More info [MS KB296405](http://support.microsoft.com/kb/296405 "The "RestrictAnonymous" Registry Value May Break the Trust to a Windows 2000 Domain [Q296405]")  
>  More info [MS KB328459](http://support.microsoft.com/kb/328459 "Troubleshooting Server Message Block Inbound Connection Limit in Windows Peer-to-Peer Workgroup [Q328459]")  
>  More info [MS KB837964](http://support.microsoft.com/kb/837964 "Security issues with LDAP NULL base connections [Q837964]")

 It is also possible to access shares using NULL sessions. For security reasons it is only possible for a set of restricted shares (Besides [IPC$](/article/winnt-ipc-share.html)) specified here:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  NullSessionPipes = "..."  
>  NullSessionShares = "..."  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  RestrictNullSessAccess = 1 (Secure = 1, Unsecure = 0, Default = No Value; Secure)  
>   
>  More info [MS KB122702](http://support.microsoft.com/kb/122702 "Using the System Account as a Service in Windows NT 3.5 [Q122702]")  
>  More info [MS KB289655](http://support.microsoft.com/kb/289655 "HOW TO: Enable Null Session Shares on a Windows 2000-Based Computer [Q289655]")  
>  More info [MS KB815458](http://support.microsoft.com/kb/815458 "You Can Use the Llsrpc Named Pipe to Add or Delete Licenses and Create New License Groups [Q815458]")  
>  More info [MS KB830070](http://support.microsoft.com/kb/830070 "Anonymous access by using a null session is possible after you configure the registry to restrict remote access [Q830070]")  
>  More info [MS KB896658](http://support.microsoft.com/kb/896658 "Windows 2000 Service Pack 4 does not update the Netserv.inf file when creating a slipstream installation [Q896658]")

 Windows XP/2003 introduced a new setting "Network Access: Do not allow anonymous enumeration of SAM accounts", which disables enumerations of SAM accounts, but still allows enumerations of shares (For Simple File Sharing): 
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\LSA\]  
>  RestrictAnonymousSAM = 1 (Default = 1)  
>   
>  More info [MS KB328459](http://support.microsoft.com/kb/328459 "Troubleshooting Server Message Block Inbound Connection Limit in Windows Peer-to-Peer Workgroup [Q328459]")

 Windows XP/2003 introduced a new setting "Network access: Let Everyone permissions apply to anonymous users", which enforces that all rights given to the Everyone-group (authenticated users) are not automatically given to the Anonymous Logon security group. Before Windows XP the Everyone-group included both authenticated users and anonymous users:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\LSA\]  
>  EveryoneIncludesAnonymous = 0 (Default = 0)  
>   
>  More info [MS KB278259](http://support.microsoft.com/kb/278259 "Everyone Group Does Not Include Anonymous Security Identifier [Q278259]")

 Related [Using NULL sessions to access this information](/article/winnt-null-session.html)  
  
 More info [MS KB823659](http://support.microsoft.com/kb/823659 "Client, service, and program incompatibilities that may occur when you modify security settings and user rights assignments [Q823659]")  
 More info [MS KB889030](http://support.microsoft.com/kb/889030 "Trust between a Windows NT domain and an Active Directory domain cannot be established or it does not work as expected [Q889030]")  