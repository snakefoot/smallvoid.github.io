---
title: 'Protected Storage'
date: '2000-06-06T16:25:40+02:00'
permalink: /article/winnt-services-protectedstorage.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Protected Storage service.'
type: post
id: 575
categories:
    - windows-2000_services
    - windows-nt4_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
tags:
    - encryption
    - password
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
  >  More Info <a href="https://www.bing.com/search?q=KB+246183+Q246183" rel="nofollow" title="You receive error message 0x80090016 or error message 0x8009000f when you try to schedule a task [Q246183]">MS KB246183</a>
4. Delete the following registry key (If it exists):
  > \[HKEY\_USERS \\.DEFAULT \\Software \\Microsoft \\Cryptography \\Providers \\Type 001\]  
  >   
  >  More Info <a href="https://www.bing.com/search?q=KB+312028+Q312028" rel="nofollow" title="Cannot Start the Terminal Server Licensing Service and Events 7024 and 37 Occur [Q312028]">MS KB312028</a>
5. Restart Windows
 
 More Info <a href="https://www.bing.com/search?q=KB+216382+Q216382" rel="nofollow" title="OLEXP: Outlook Express Does Not Save the Mail Server Logon Password [Q216382]">MS KB216382</a>  
 More Info <a href="https://www.bing.com/search?q=KB+264033+Q264033" rel="nofollow" title="Protected Storage Always Prompts for Password After Using GhostWalker [Q264033]">MS KB264033</a>  
 More Info <a href="https://www.bing.com/search?q=KB+264672+Q264672" rel="nofollow" title="OLEXP: Your Outlook Express Password Is Not Retained in Windows 2000 or XP [Q264672]">MS KB264672</a>  
 More Info <a href="https://www.bing.com/search?q=KB+275465+Q275465" rel="nofollow" title="Your password is not retained when Outlook 2000 is installed with the Corporate or Workgroup option in Windows 2000 or Windows XP [Q275465]">MS KB275465</a> (Replaces MS KB259416)  
 More Info <a href="https://www.bing.com/search?q=KB+290684+Q290684" rel="nofollow" title="Save password setting not retained in Outlook [Q290684]">MS KB290684</a>  
 More Info <a href="https://www.bing.com/search?q=KB+306895+Q306895" rel="nofollow" title="AutoComplete Does Not Save Username and Password [Q306895]">MS KB306895</a>  
  
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