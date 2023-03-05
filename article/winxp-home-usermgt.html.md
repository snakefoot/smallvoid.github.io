---
title: 'Advanced User Management in Windows XP Home'
date: '2003-09-26T00:04:14+02:00'
status: publish
permalink: /article/winxp-home-usermgt.html
author: Snakefoot
excerpt: 'Hidden Control Panel applet that includes more options for account management.'
type: post
id: 153
category:
    - 'User Security'
tag:
    - crippled
    - user-account
post_format: []
tags:
    - 'user-account,crippled'
---
The **User Accounts**-applet in the Control Panel for WinXP Home is rather limited, but it is possible to get access to a more advanced User Accounts-applet with this command (Similar to WinXP Pro's "control userwords2"):

> control userpasswords2

 This applet allows one to: - Configure [Automatic Login](/article/winnt-automatic-logon.html) by removing check from "User must enter a user name and password to use this computer".
- Change password on the "hidden" Administrator account.
- Delete/Modify "hidden"/"disappeared" user accounts.
- Enforce the requirement of pressing CTRL + ALT + DEL before login can be performed.
 
 Note one should not use this applet to create new user accounts in WinXP Home, as the accounts will not work properly when trying to login.  
  
 Note the Power Users group are not supported by WinXP Home, so one should not try to assign such privileges to an existing account, or else errors like these will appear:
 > *The user could not be added because the following error has occurred, The group name could not be found: When creating a new user and make it member of the 'Power Users' group.  
>   
>  The group membership for &lt;ComputerName\\UserName&gt; could not be updated : When updating an existing user, adding him to the 'Power Users group'.*

 More Info [MS KB279783](http://support.microsoft.com/kb/279783 "HOW TO: Create and Configure User Accounts in Windows XP [Q279783]")  
 More Info [MS KB817365](http://support.microsoft.com/kb/817365 "Creation of user in the 'Power Users' group with 'Control Userpasswords2' [Q817365]")  