---
title: 'Moving the userprofile to a different location'
date: '2002-06-25T18:02:16+02:00'
status: publish
permalink: /article/winnt-move-userprofile.html
author: Snakefoot
excerpt: 'How to move the location of the user profile for either backup or after restore.'
type: post
id: 259
category:
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - user-account
    - user-profile
post_format: []
tags:
    - 'user-profile,user-account'
---
By default WinNT places all user profiles on the %SYSTEMDRIVE%, which makes sure that it have access to the user profiles even if the drive letters move.  
  
 One can move the location of a profile to a different drive :

- It will not be taking space on the %SYSTEMDRIVE%
- It will not be lost when reformatting the %SYSTEMDRIVE%
- It will allow one to group the profile with other personal folders and files.
- It will also move the location of [Temporary Files](/article/temporary-directory.html), [Outlook Email](/article/outlook-express-backup-email.html), [Outlook Address Book](/article/outlook-express-address-book.html), [Temporary Internet Files](/article/ie-temporary-internet-files.html), [Favorites](/article/ie-backup-favorites.html) and My Documents to the new location, unless the default location has been changed.
- It will NOT move the contents of [Temporary Files](/article/temporary-directory.html), [Outlook Email](/article/outlook-express-backup-email.html), [Outlook Address Book](/article/outlook-express-address-book.html), [Temporary Internet Files](/article/ie-temporary-internet-files.html). If you have changed the default location of those items, then no problem.
 
 Move the location of existing profile :
1. Logon to the computer with a profile with Administrator rights (Not the profile you want to move)
2. Right click "My Computer" and select "Properties"
3. Win2k users has to select the "User Profiles" fan
4. WinXP users has to select the "Advanced" fan and press "Settings..." in the "User Profile" section.
5. Select the profile you want to move and press the "Copy To..." button
6. Select the location of where you want to store the profile (Note with "Permitted" you can change rights to the profile and thus give the profile to a different user with lower rights)
7. After it has copied the profile, start regedit an change the profile location for the user (Before changing write down the current location so you can delete it later):
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\ProfileList \\ {SID}\]  
  >  ProfileImagePath = "D:\\Personal\\Profile\\Username"
8. To verify that everything is correct. Logon with the changed profile and right click the Start Button and select "explore" to see if it is using the Start Menu in the new location.
 
 Restore an existing profile after reformat/repair:
1. Logon to the computer with a profile with Administrator rights
2. Right click "My Computer" and select "Manage"
3. In the tree select "System Tools" -&gt; "Local Users and Groups" -&gt; "Users"
4. Right click the pane showing the current users and select "New User..."
5. Set the wanted username, password and access rights (Member Of)
6. Logoff and logon with the new user (This will create the right entries in registry)
7. Logoff and logon with the a profile with Administrator rights
8. Restore the profile into the profile-directory for the newly created user. 
  - For Win2k/WinXP this is by default within: "C:\\Documents and Settings"
  - For WinNT4 this is by default within: "C:\\WinNT\\Profiles"
  - Or one can change the "ProfileImagePath" for the newly created user, so it points to the directory containing the profile to restore:
      > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\ProfileList \\ {SID}\]  
      >  ProfileImagePath = "D:\\Personal\\Profile\\Username"
9. [Make sure the new user has ownership of the restored profile](/article/ntfs-access-control.html).
10. Logoff and logon with the new user (Which now uses the restored profile)
11. All settings should be restored as before (Passwords are most likely forgotten)
 
 Note the Security identifier (SID) is unique for each user. The easiest way to see what SID belongs to which user is look at the "ProfileImagePath" value for each SID and then see the username in the path. One can also use the [GetSID](http://www.microsoft.com/windows2000/techinfo/reskit/tools/existing/getsid-o.asp) and if one need change the SID use [NewSID](http://www.sysinternals.com/ntw2k/source/newsid.shtml).  
  
 Note one shouldn't move the builtin Administrator profile, and one shouldn't use the built in Administrator account at all, except in emergency where all other profiles have been ruined. If needing an Administrator profile create a new one and let it be member of the Administrator group.  
  
 Note to keep up security, one should convert partitions with userprofiles to NTFS.  
  
 Note for optimal security one shouldn't give Administrator group rights to your account for daily use, as all programs you run will get Administrator rights including trojans. Instead use the group "PowerUsers". And if you need to do something which requires Administrator rights then logoff and logon as Administrator or use [RunAs](/article/winnt-services-seclogon.html).  
  
 More Info [MS KB162001](http://support.microsoft.com/kb/162001 "Do Not Disk Duplicate Installed Versions of Windows [Q162001]")  
 More Info [MS KB214470](http://support.microsoft.com/kb/214470 "How to Move the Location of a Locally Cached Profile [Q214470]")  
 More Info [MS KB236621](http://support.microsoft.com/kb/236621 "Cannot Move or Rename the Documents and Settings Folder [Q236621]")  
 More Info [MS KB811151](http://support.microsoft.com/kb/811151 "How to Copy User Data to a New User Profile [Q811151]")  