---
title: 'How to enable Win9x filesharing in Windows XP'
date: '2002-05-28T01:52:46+02:00'
status: publish
permalink: /article/winxp-win9x-filesharing.html
author: Snakefoot
excerpt: 'Activating the insecure guest account for easy file sharing.'
type: post
id: 149
category:
    - 'File Sharing'
tag:
    - guest-account
post_format: []
tags:
    - guest-account
---
The default configuration of WinXP is to use Simple Filesharing, which is just as easy as the Win9x filesharing. Just right-click a folder and select share. This share will now be available to anyone without needing to provide password or anything.  
 Simple Filesharing uses the Guest account (even if the account is disabled), but it requires that "Access this computer from the network" includes Everyone and Guest.  
  
<a name="SIMPLE_FILESHARING"></a> If using WinXP Pro and wants mixed environment where guest should have access to a limited set of folders and special users access more folders, then one have to disable **Simple Filesharing** (Not possible in WinXP Home):

1. Start Button -&gt; My Computer
2. In the menu of My Computer select "Tools" -&gt; "Folder Options"
3. In "Folder Options" select the "View" fan
4. Uncheck the setting "Use Simple File Sharing (Recommended)"  
    
   This change should be reflected in this DWORD registry key:
  > \[HKEY\_LOCAK\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Lsa\]  
  >  ForceGuest = 0  
  >   
  >  More Info [MS KB290403](http://support.microsoft.com/kb/290403 "How to Set Security in Windows XP Professional That Is Installed in a Workgroup [Q290403]")  
  >  More Info [MS KB307874](http://support.microsoft.com/kb/307874 "How to Set Security in Windows XP Professional That Is Installed in a Workgroup [Q307874]")
 
 It is advised to create an account with a secure password for each user, who should have access to a share. But some times it is just too cumbersome, even if one creates a group containing all the users which should have access.  
  
 Enable the guest account, so everyone will use that to access your shares:
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. Expand "Local Users" -&gt; "Users"
3. Right click the "Guest" account and select "Properties"
4. Uncheck "Account is disabled"
 
 Enable listing of shares [More Info](/article/winnt-restrict-anonymous.html):
 1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. Expand "Local Policies" -&gt; "Security options"
3. Check that the setting "Network access: Do not allow anonymous enumeration of SAM accounts and shares" is set to disabled
 
<a name="EMPTY_PASSWORD"></a> Enable access of shares using empty password:
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. Expand "Local Policies" -&gt; "Security options"
3. Check that "Accounts: Limit local account use of blank passwords to console login only" is disabled.  
    
   This change should be reflected in this DWORD registry key:
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Lsa\]  
  >  LimitBlankPasswordUse = 0  
  >   
  >  Note this will leave all accounts with no password unprotected. Making it possible to perform login over the network.
 
 Make sure your security policy allows network access for everyone
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. Expand "Local Policies" -&gt; "User Rights Assignment"
3. Check that "Access this computer from the network" has these groups included "Guests" and "Everyone"
4. Check that "Deny access to this computer from the network" doesn't include "Guests" and "Everyone"
 
 If wanting to give extra rights to some accounts, then disable that all network logins gets guest access when in a workgroup:
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. Expand "Local Policies" -&gt; "Security options"
3. Check that "Network access: Sharing and security model for local accounts" is set to "Classic: local users authenticate as themselves"
 
 Remember to reboot to make sure settings are activated.  
  
 Note the above settings only opens the policies for allowing guests to access the computer. When making a share one have to allow guests to access the share, and if the folder being shared is placed on a NTFS drive, then one have to [Set NTFS permissions to allow guest access](/article/ntfs-access-control.html).  
  
 Related [Creating a Local Area Network and troubleshooting](/article/troubleshooting-network.html)  
  
 More Info [Windows XP Professional File Sharing](http://www.practicallynetworked.com/sharing/xp_filesharing/index.htm)  
 More Info [Windows XP Professional Security Policies](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/sotopnode.mspx)  
 More info [MS KB304040](http://support.microsoft.com/kb/304040 "Description of File Sharing and Permissions in Windows XP [Q304040]")  