---
title: 'Configure the login and Welcome Screen in Vista'
date: '2007-10-05T02:49:56+02:00'
status: publish
permalink: /article/vista-welcome-screen.html
author: Snakefoot
excerpt: 'Windows Vista does not have the classic logon screen, which has been replaced by the Welcome Screen.'
type: post
id: 750
category:
    - 'User Security'
tag:
    - automatic-login
    - user-account
    - welcome-screen
    - windows-login
post_format: []
tags:
    - 'windows-login,welcome-screen,user-account,automatic-login'
---
The Welcome Screen is enabled by default and is shown at startup, where one can choose one of the available user-accounts (Just like in WinXP). The old classic logon screen is no longer available.

##### Secure login screen with CTRL + ALT + DEL before login

1. Press the **Start**-button and run this command:
   > control userpasswords2
2. Change to the **Advanced**-tab and enable **Require users to press CTRL+ALT+DEL**  
    
   This change should match the following DWORD registry setting:
   > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
   >  DisableCAD = 0
  
   This change should also match the following Local Security Policy (secpol.msc) -&gt; Local Policies -&gt; Security Options -&gt; "Interactive logon: Do not require CTRL+ALT+DEL".

![](/tweak/winnt/pictures/vista-ctrl-alt-del.jpg)

 Note after pressing CTRL + ALT + DEL then the normal Welcome Screen will show with all the pretty user account icons.  
##### Only display the user name and password prompt at login

1. Open **Control Panel** and select **System and Maintenance**
2. Select **Administrative Tools** and double-click **Local Security Policy** (secpol.msc)
3. Expand **Local Policies** to **Security Options**
4. Enable **Interactive logon: Do not display last user name**  
    
   This change should match the following DWORD registry setting:
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\System\]  
  >  DontDisplayLastUserName = 1

![](/tweak/winnt/pictures/vista-no-last-user.jpg)

 Now it will only display the input fields for username and password, and it will no longer display all the available accounts with their user names and icons.  
##### Hide a single user account from the Welcome Screen

 By adding the username of the account to a special list in the registry, then it will no longer appear on the Welcome Screen. Just create DWORD registry value at the following location:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon \\SpecialAccounts \\UserList\]  
>  NameOfTheUser = 0 (1 = Show, 0 = Hide)  
>   
>  More Info [MS KB942956](http://support.microsoft.com/kb/942956 "Information for advanced users about the changes to the built-in administrator account in Windows Vista")

 Note in Vista the Administrator account is disabled by default and when activated, then it will be displayed on the Welcome Screen automatically. More Info [MS KB926183](http://support.microsoft.com/kb/926183 "The administrator account does not appear on the Windows Vista Welcome screen")

##### Customize the picture shown on the Welcome screen

 To change the picture shown on the logon screen for a user:
1. Open **Control Panel** and select **User Accounts**-
2. Click **Change Your Picture** and select the picture you want.
 
 Note the available user account pictures are located in the following directory:
 > C:\\ProgramData\\Microsoft\\User Account Pictures\\Default Pictures

 <a name="default_picture"></a> Note the default user account picture is located here (Can be replaced with another 128x128 pixel bmp image):
 > C:\\ProgramData\\Microsoft\\User Account Pictures\\user.bmp  
 >  C:\\ProgramData\\Microsoft\\User Account Pictures\\guest.bmp

 Note the picture currently selected by the user is located here:
 > C:\\Users\\&lt;username&gt;\\AppData\\Local\\Temp\\&lt;username&gt;.tmp.bmp

##### Prevent users from changing their logon picture

 This can be useful is wanting all users to use the company logo as user logon picture.
1. **Start** and **Run...**
   > gpedit.msc
2. Expand to **Local Computer Policy** -&gt; **Computer Configuration** -&gt; **Administrative Templates** -&gt; **Control Panel** -&gt; **User Accounts**
3. Double-click **Apply the default user logon picture to all users** and change to **Enabled**  
    
   This change should match the following DWORD registry setting:
   > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
   >  UseDefaultTile = 1
 
 Note the picture shown on the Start-menu will be replaced with an empty frame, when enabling this policy.  
  
 Note to change the default picture, just overwrite this bitmap file with another picture-file (128x128 pixel bmp image). If this bitmap-file doesn't exist then it will show an empty frame on the Welcome Screen.
 > C:\\ProgramData\\Microsoft\\User Account Pictures\\user.bmp

##### Disable the Welcome Screen by enabling automatic login

 [Automatic Login](/article/winnt-automatic-logon.html) can be enabled, which will bypass the need to logon (turns off the Welcome Screen). This is done with the following steps:
 1. Run this this command to open the advanced user management:
    > control userpasswords2
 2. Uncheck **"Users must enter a username and password to use this computer"** and provide the username and password for the account to use by default.
 
 Credits [Rob Farley](http://msmvps.com/blogs/robfarley/)