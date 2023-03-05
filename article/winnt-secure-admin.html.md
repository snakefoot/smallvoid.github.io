---
title: 'Securing the local Administrator account'
date: '2001-09-01T23:36:51+02:00'
status: publish
permalink: /article/winnt-secure-admin.html
author: Snakefoot
excerpt: 'Protecting the Administrator account from unauthorized access.'
type: post
id: 152
category:
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - administrator
    - group-policy
    - password
    - remote-access
    - user-account
    - windows-login
post_format: []
tags:
    - 'administrator,password,remote-access,windows-login,user-account,group-policy'
---
The Administrator account is the default account created during the install of Windows. It doesn't have different rights compared to other accounts that are part of the Administrators-group. The only difference is that the name of the account is known by many people.  
  
 Different options are available for protecting the Administrator account (which can be combined):

- Use a firewall to block all access to the machine from network.
- Deny network logon with accounts included in the Administrator-group using group policies: 
  1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
  2. In the tree-view go to "Local Policies" -&gt; "User Rights Assignment"
  3. Go to the entry "Deny access to this computer from the network" and double click it to add the Administrators-group.
   
   More info [MS KB281140](http://support.microsoft.com/kb/281140 "HOW TO: Disable the Local Administrator Account in Windows [Q281140]")
- Change the name of the Administrator account: 
  1. Open the **Control Panel** and double click **Users and Passwords**
  2. On the **Users**-tab tick **Users must enter a username and password to use this computer**
  3. In the list **Users for this computer:** select the Administrator account
  4. Click **Properties**-button and in the new window change the **User name** to something you can remember yourself
   
   Related [Advanced User Management in Windows XP Home](/article/winxp-home-usermgt.html)
- Setup a password for the Administrator account:  
    
   Windows XP will by default block [network access to accounts with no password](/article/winxp-win9x-filesharing.html#EMPTY_PASSWORD), and configures the Administrator account to have no password. Don't set a password for the Administrator account, unless wanting to enable access to the account from the network. 
  1. Open the **Control Panel** and double click **Users and Passwords**
  2. On the **Users**-tab tick **Users must enter a username and password to use this computer**
  3. In the list **Users for this computer:** select the Administrator account
  4. Click **Set Password...**-button and in the new window type in the new password.
- Use PassProp to protect the built-in administrator account from being attacked by dictionary password crackers. The built-in administrator account can never be disabled by default, so if having guessed the built-in administrator account name, then it can be attacked without the account becoming disabled. The PassProp utility can change the administrator account so it will react to password lockout policies. More Info [The Administrator Accounts Security Planning Guide](http://www.microsoft.com/technet/security/guidance/serversecurity/administratoraccounts/aapgch03.mspx)
 
 Note one can also rename the Administrator account using the "Local Users and Groups" MMC-Snapin:
1. Press **Start**-button and select **Run...** this command:
   > lusrmgr.msc
2. Select the folder **Users** and right click the Administrator account and select **Rename**
3. Change the name to something you can remember
 
 Note one can also rename the Administrator account using the group policy editor:
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the tree-view go to **Local Policies** -&gt; **Security Options**
3. In the list find the item **Rename Administrator Account** and double click it to change it to something you can remember yourself
 
 More info [MS KB298252](http://support.microsoft.com/kb/298252 "Cannot Change the Password for the Administrator Account in User Accounts in Control Panel [Q298252]")  
 More info [MS KB320053](http://support.microsoft.com/kb/320053 "HOW TO: Rename the Administrator and Guest Account in Windows 2000 [Q320053]")  