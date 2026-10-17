---
title: 'Configure Automatic Logon in Windows NT'
date: '2003-02-28T00:11:51+01:00'
permalink: /article/winnt-automatic-logon.html
author: Snakefoot
excerpt: 'Enabling automatic login so one doesn''t have to type username and password at every boot.'
type: post
id: 154
categories:
    - windows-2003_user-security
    - windows-nt4_user-security
    - windows-xp_user-security
    - windows-2000_user-security
tags:
    - automatic-login
    - user-account
    - welcome-screen
    - windows-domain
    - windows-login
---
It is possible to make the logon automatically, which is very convenient when using a [strong password to avoid network attacks](/article/winnt-secure-admin.html) but still wants to have easy physical access to the machine.  
  
 The easiest (and the most secure) way to enable automatic logon:

- Press **Start**-button and open the **Control Panel**
- Double click the **Users and Passwords** (If using WinXP Home then [read this](/article/winxp-home-usermgt.html))
- Uncheck **Users must enter a user name and password to use this computer**
- It will prompt for a username and password for the automatic login. 
  - The password entered will be encrypted and saved in the registry here (Will also happen if using Tweak UI to configure Automatic Logon):
  > \[HKEY\_LOCAL\_MACHINE \\SECURITY \\Policy \\Secrets \\DefaultPassword\]
- Press **Ok** and reboot to test that the automatic login is now working
 
 WinXP will automatically activate automatic logon if the following conditions are true:
- The [Welcome screen](/article/winxp-welcome-screen.html) must be enabled
- Guest account access must be turned off
- There must be only one user account on the computer 
  - System Accounts must be added to the [SpecialAccounts Userlist](/article/winxp-welcome-screen.html#SPECIALACCOUNTS) as hidden. After installing Service Pack 2 then a new account ASPNET is added that is not hidden, so automatic login stops working.
- The user account must not have a password
 
 Note it is also possible to manually enable automatic login using the registry, but with the exception that the password is placed in the registry as plain text:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  DefaultUserName = "MyUserName"  
>  DefaultPassword = "MyPassword"  
>  DefaultDomainName = "MyNetworkDomain or MyComputerName"  
>  AutoAdminLogon = "1"

 Note the security policy "Don't Display Last Username" must be disabled for the automatic logon to work. This can be done with this STRING registry value:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  DontDisplayLastUserName = "0"

 Note in Win2k/XP one can force autologon, so when a user logs off it will automatically logon again (Though it will disable [remote logon](/article/windows-remote-desktop.html)):
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  ForceAutoLogon = "1"

 Note it is possible bypass the automatic logon in case one need to access another account than the default. This is done by holding down the keyboard key SHIFT while Windows is starting or holding down SHIFT while logging off (If using an USB keyboard then USB legacy support must be enabled in the motherboard BIOS). This bypass can be disabled with this STRING registry key:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  IgnoreShiftOverride = "1"

 More info <a href="https://www.bing.com/search?q=KB%2097597%20Q97597" rel="nofollow" title="How to Enable Automatic Logon in Windows NT 3.x and 4.0 [Q97597]">MS KB97597</a>  
 More info <a href="https://www.bing.com/search?q=KB%20114615%20Q114615" rel="nofollow" title="Bypassing Automatic Logon in Windows NT [Q114615]">MS KB114615</a>  
 More info <a href="https://www.bing.com/search?q=KB%20167364%20Q167364" rel="nofollow" title="Automating AUTOADMINLOGON Locally When Joining a Domain [Q167364]">MS KB167364</a>  
 More info <a href="https://www.bing.com/search?q=KB%20234333%20Q234333" rel="nofollow" title="Prompt for User Credentials After Specifying Not to Be Prompted [Q234333]">MS KB234333</a>  
 More info <a href="https://www.bing.com/search?q=KB%20234562%20Q234562" rel="nofollow" title="How to Enable Automatic Logon in Windows 2000 Pro [Q234562]">MS KB234562</a>  
 More info <a href="https://www.bing.com/search?q=KB%20282866%20Q282866" rel="nofollow" title="HOW TO: Automatically Log On a User Account in Windows XP [Q282866]">MS KB282866</a>  
 More info <a href="https://www.bing.com/search?q=KB%20300433%20Q300433" rel="nofollow" title="The 'Administrator Logon' Dialog Box May Be Hidden Under the Welcome Screen or 'The System Could Not Log You on' Message May Be Displayed [Q300433]">MS KB300433</a>  
 More info <a href="https://www.bing.com/search?q=KB%20310584%20Q310584" rel="nofollow" title="How to Enable Automatic Logon in Windows 2000 [Q310584]">MS KB310584</a>  
 More info <a href="https://www.bing.com/search?q=KB%20315231%20Q315231" rel="nofollow" title="How to Enable Automatic Logon in Windows XP [Q315231]">MS KB315231</a>  
 More info <a href="https://www.bing.com/search?q=KB%20324737%20Q324737" rel="nofollow" title="How to Enable Automatic Logon in Windows 2003 [Q324737]">MS KB324737</a>  