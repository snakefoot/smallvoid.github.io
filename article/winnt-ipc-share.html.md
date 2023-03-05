---
title: 'Description of the IPC$ share'
date: '2003-03-03T16:07:58+01:00'
status: publish
permalink: /article/winnt-ipc-share.html
author: Snakefoot
excerpt: 'How the IPC$ share makes it possible for clients to access shares on the server.'
type: post
id: 146
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - anonymous-access
    - guest-account
    - inter-proces-communication
    - network-share
    - remote-procedure-call
post_format: []
tags:
    - 'inter-proces-communication,remote-procedure-call,network-share,anonymous-access,guest-account'
---
The IPC$ is a [hidden share](/article/hidden-file-shares.html) maintained by the [Server service](/article/winnt-services-lanmanserver.html) (Disabling the service will remove the share). The IPC$ share is used for Inter Proces Communication by using RPC (Remote Procedure Call), allowing the client to send different commands to the server:

- List all shares
- List all users
- List files within a share
- Stop/Start services
- ...
 
 Certain commands can be [accessed anonymously](/article/winnt-restrict-anonymous.html) through a [NULL session](/article/winnt-null-session.html) depending on the configuration of the server. If the command cannot be called anonymously, then the client has to authenticate. Access is granted if the client can provide proper credentials (username and password), that matches an account on the server. If not able to do this, then the user at the client machine will get an error like:
> *IPC$, The domain password you supplied is not correct  
>   
>  You must supply a password to make this connection:  
>   
>  Incorrect password or unknown username for:*

 <a name="net_use"></a> Note it is possible to access the IPC$ share of a server by using a different credentials, than those used when logging on the client machine. (Even if needing to use a domain-user to access a server from outside the domain). > net use q: \\\\10.0.0.2\\c$ \[password\] /user:\[domain\\\]username

 Note to block access to Remote Procedure Call (RPC), then one should ensure that the firewall blocks the following network ports: - TCP Port 135 - RPC Endpoint Mapper
- UDP Port 137 - Netbios
- UDP Port 138 - Netbios
- TCP Port 139 - Netbios
- TCP and UDP Port 445 - Named Pipes
 
 Note Windows 95/98/Me doesn't support logon with different credentials. Therefore one have to make sure the userid and password on the Win9x machine matches one of the accounts on the WinNT machine. This can be done by using one of the following options:
- Create an account on the WinNT machine which matches the username and password (If any) used on the Win9x machine. 
  - If the account already exist, then try to reenter the account password for the account (And check the password doesn't expire)
- [Create an account on the Win9x machine](http://support.microsoft.com/kb/176059 "Description of the Users Tool in Control Panel [Q176059]") which matches the username and password of an account on the WinNT machine and then logon to Win9x with the new account.
- Activate the guest account, though it is not recommended: 
  - [How to enable Win9x filesharing in Windows 2000](/article/win2k-win9x-filesharing.html)
  - [How to enable Win9x filesharing in Windows XP](/article/winxp-win9x-filesharing.html)
 
 Note if sure that the account is properly setup then one can configure an [audit](/article/winnt-security-audit.html) to see what account name is used to login to the machine.  
  
 More Info [MS KB101150](http://support.microsoft.com/kb/101150 "Operating Characteristics and Restrictions of Named Pipes [Q101150]")  
 More Info [MS KB139592](http://support.microsoft.com/kb/139592 "Prompted for Password When Connecting to Windows NT [Q139592]")  
 More Info [MS KB162325](http://support.microsoft.com/kb/162325 "Err Msg: You Must Provide a Password to Make This Connection [Q162325]")  
 More Info [MS KB258717](http://support.microsoft.com/kb/258717 "Configuring Windows 2000 Professional to Work in a Peer-to-Peer Workgroup [Q258717]")  
 More Info [MS KB262916](http://support.microsoft.com/kb/262916 "Unable to Connect to Network Share When Netlogon Service Is Not Started [Q262916]")  