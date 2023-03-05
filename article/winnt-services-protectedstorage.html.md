---
title: 'Protected Storage'
date: '2000-06-06T16:25:40+02:00'
status: publish
permalink: /article/winnt-services-protectedstorage.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Protected Storage service.'
type: post
id: 575
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - encryption
    - password
post_format: []
tags:
    - 'password,encryption'
---
##### Description:

 Is used to encrypt and store secure information like this - SSL certificates
- Passwords for programs (like Outlook, Outlook Express, etc.)
- Info stored by Profile Assistant
- Info maintained by MS Wallet
- Digitally signed S/MIME keys.
 
 Note if this service is set to manual it will cause Outlook Express to take a long time to start, because it has to wait for this service to load first.  
  
 Note if this service is stopped or disabled, private keys will be inaccessible, certificate server will not operate, S/MIME &amp; SSL will not work and smart card logon will fail.  
  
 Note if Protected Storage becomes corrupt, then it might fail to start or fail to provide services. To reset Protected Storage:
1. Boot in safemode
2. Execute this command:
   > net stop ProtectedStorage
3. Move the contents of the this folder to another folder for safe keeping:
  > C:\\Documents and Settings\\All Users\\Application Data\\Microsoft\\Crypto\\RSA\\S-1-5-18  
  >   
  >  More Info [MS KB246183](http://support.microsoft.com/kb/246183 "You receive error message 0x80090016 or error message 0x8009000f when you try to schedule a task [Q246183]")
4. Delete the following registry key (If it exists):
  > \[HKEY\_USERS \\.DEFAULT \\Software \\Microsoft \\Cryptography \\Providers \\Type 001\]  
  >   
  >  More Info [MS KB312028](http://support.microsoft.com/kb/312028 "Cannot Start the Terminal Server Licensing Service and Events 7024 and 37 Occur [Q312028]")
5. Restart Windows
 
 More Info [MS KB216382](http://support.microsoft.com/kb/216382 "OLEXP: Outlook Express Does Not Save the Mail Server Logon Password [Q216382]")  
 More Info [MS KB264033](http://support.microsoft.com/kb/264033 "Protected Storage Always Prompts for Password After Using GhostWalker [Q264033]")  
 More Info [MS KB264672](http://support.microsoft.com/kb/264672 "OLEXP: Your Outlook Express Password Is Not Retained in Windows 2000 or XP [Q264672]")  
 More Info [MS KB275465](http://support.microsoft.com/kb/275465 "Your password is not retained when Outlook 2000 is installed with the Corporate or Workgroup option in Windows 2000 or Windows XP [Q275465]") (Replaces MS KB259416)  
 More Info [MS KB290684](http://support.microsoft.com/kb/290684 "Save password setting not retained in Outlook [Q290684]")  
 More Info [MS KB306895](http://support.microsoft.com/kb/306895 "AutoComplete Does Not Save Username and Password [Q306895]")  
  
##### Recommended State:

- Manual.

##### Default State:

- Vista/Win7: Manual
- WinNT4/Win2k/WinXP/Win2k3: Automatic

##### Process Name:

- Win2k/WinNT4+IE4: [services.exe](/article/winnt-services-wrapper.html) (ProtectedStorage)
- WinXP/Win2k3/Vista/Win7: [lsass.exe](/article/winnt-services-wrapper.html) (ProtectedStorage)

##### Supports:

- [Wireless Configuration](/article/winnt-services-wzcsvc.html) (Win2k SP4+ only)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)