---
title: 'How to enable Win9x filesharing in Windows 2000'
date: '2001-09-01T13:24:10+02:00'
status: publish
permalink: /article/win2k-win9x-filesharing.html
author: Snakefoot
excerpt: 'Activating the insecure guest account for easy file sharing.'
type: post
id: 144
category:
    - 'File Sharing'
tag:
    - guest-account
    - microsoft-network
post_format: []
tags:
    - 'guest-account,microsoft-network'
---
It is advised to create an account with a secure password for each user, who should have access to a share [MS KB258717](http://support.microsoft.com/kb/258717 "Configuring Windows 2000 Professional to Work in a Peer-to-Peer Workgroup [Q258717]"). But some times it is just too cumbersome, even if one creates a group containing all the users which should have access.  
  
 Enable the guest account, so everyone will use that to access your shares:

1. Go to "Computer Management" -&gt; "Local Users and Groups" -&gt; "Users"
2. Double click the "Guest" user
3. Make sure the checkbox "Account is disabled" is unchecked and press "Ok" button
4. Right click the "Guest" user and select "Set Password" and just let the password be empty
5. Now make your shares using the Guest account and everyone should have access with no password. (Remember that by default Win2k gives full permissions to the shares you create)
 
 Enable listing of your shares [More Info](/article/winnt-restrict-anonymous.html):
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the treeview go to "Local Policies" -&gt; "Security Options"
3. Check that the setting "Additional restriction for anonymous connection" is set to "None, Rely on default permissions"
 
 Make sure your security policy allow network access for everyone:
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the treeview go to "Local Policies" -&gt; "User Rights Assignment"
3. Check that "Access this computer from the network" has these groups included "Guests" and "Everyone"
4. Check that "Deny access to this computer from the network" doesn't contain the above groups
 
 Remember to reboot after setting security policies so they take effect.  
  
 Note the above settings only opens the policies for allowing guests to access the computer. When making a share one have to allow guests to access the share, and if the folder being shared is placed on a NTFS drive, then one have to [Set NTFS permissions to allow guest access](/article/ntfs-access-control.html).  
  
 If one continue to have problems with security policies, then try to import default policies "basicwk.inf" and "compatws.inf" [MS KB234926](http://support.microsoft.com/kb/234926 "Windows 2000 Security Templates Are Incremental [Q234926]")  
  
 Related [Creating a Local Area Network and troubleshooting](/article/troubleshooting-network.html)