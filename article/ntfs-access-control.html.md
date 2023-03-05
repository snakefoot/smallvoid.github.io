---
title: 'Restrict access to the files stored on NTFS partitions'
date: '2001-01-01T02:13:39+01:00'
status: publish
permalink: /article/ntfs-access-control.html
author: Snakefoot
excerpt: 'Using access control lists to improve the security for NTFS partitions.'
type: post
id: 150
category:
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - access-control-list
    - ntfs
post_format: []
tags:
    - 'ntfs,access-control-list'
---
NTFS partitions have the capability of handling access control lists (ACL) for the folders/directories on the partition. This can be used to control who is allowed to get access to certain folders.  
  
 For example one can restrict access to the NTFS partition/drive/folder so only authenticated users have access:

1. Open **My Computer**
2. Right-click the NTFS-partition and select **Properties** (Or a folder on the partition)
3. In the new dialog pick the **Security**-fan 
  - One has to be part of the Administrator-group to use this fan.
  - If using WinXP Pro then one has to [disable Simple Filesharing](/article/winxp-win9x-filesharing.html#SIMPLE_FILESHARING) to access this fan.
  - If using WinXP Home then one has to boot in safemode to access this fan.
4. In the **Security**-fan one can do the following: 
  - Take ownership of the partition: 
      1. Press the **Advanced**-button
      2. Select the **Owner**-fan
      3. Select the **Administrators**-group
      4. Check **Replace owner on subcontainers and objects**-box
      5. Press **Ok**-button
      6. Press **Apply**-button
  - Restrict access to the NTFS partition so only authenticated users have access: 
      1. Remove the **Everyone**-group and instead add **Authenticated Users**-group
      2. Select the **Authenticated Users**-group and make sure it has **Full Control**
      3. Press **Apply**-button
  - Apply the above restriction to all subfolders (Do NOT do this on the system-partition): 
      1. Press the **Advanced**-button
      2. Select the **Permissions**-fan
      3. Tick "Replace/Reset Permissions..."
      4. Press **Ok**-button
      5. Press **Apply**-button
 
 Note one can also use this to take ownership of NTFS partitions when getting access denied. This can be useful when installing a new harddisk with existing NTFS partitions. Because the harddisk usually comes from another computer, where it was configured only to be owned by the users on the other computer.  
  
 Note one can also use this to take ownership of user folders, which can be useful in the situation where one is doing a [Restore of an existing profile after reformat/repair](/article/winnt-move-userprofile.html)  
  
 Note one can also use this feature to provide extra control of who has access to network shares. Even if a user has authenticated to get access to a share, then it is possible to block certain folders within the share using NTFS permissions. See also [Access-based Enumeration](/article/access-based-enumeration.html).  
  
 Note if having [Created a dummy Administrator-account](/article/winnt-secure-admin.html), then one should make sure it doesn't have access to any of the NTFS partitions in the machine. But be sure that it is the dummy account and NOT the Administrators-group.  
  
 Note if having enabled the guest-account, then one should consider to only give read-access to the required NTFS partitions.  
  
 More Info [MS KB148437](http://support.microsoft.com/kb/148437 "Default NTFS Permissions in Windows NT [Q148437]")  
 More Info [MS KB153094](http://support.microsoft.com/kb/153094 "Restoring Default Permissions to Windows NT System Files [Q153094]")  
 More Info [MS KB244600](http://support.microsoft.com/kb/244600 "Default NTFS Permissions in Windows 2000 [Q244600]")  
 More Info [MS KB266118](http://support.microsoft.com/kb/266118 "How to restore the default NTFS permissions for Windows 2000 [Q266118]")  
 More Info [MS KB268019](http://support.microsoft.com/kb/268019 "HOW TO: Take Ownership of Files [Q268019]")  
 More Info [MS KB301195](http://support.microsoft.com/kb/301195 "HOW TO: Configure Security for Files and Folders on a Network (Domain) in Windows 2000 [Q301195]")  
 More Info [MS KB308418](http://support.microsoft.com/kb/308418 "How to set, view, change, or remove file and folder permissions in Windows XP [Q308418]")  
 More Info [MS KB308419](http://support.microsoft.com/kb/308419 "HOW TO: Set, View, Change, or Remove Special Permissions for Files and Folders in Windows XP [Q308419]")  
 More Info [MS KB308421](http://support.microsoft.com/kb/308421 "How to take ownership of a file or folder in Windows XP [Q308421]")  
 More Info [MS KB318754](http://support.microsoft.com/kb/318754 "HOW TO: Use Xcacls.exe to Modify NTFS Permissions [Q318754]")  
 More Info [MS KB324067](http://support.microsoft.com/kb/324067 "HOW TO: Set Folder Security for Shared Folders [Q324067]")  
 More Info [MS KB325361](http://support.microsoft.com/kb/325361 "HOW TO: Configure Security for Files and Folders on a Network in Windows Server 2003 [Q325361]")  
 More Info [MS KB810881](http://support.microsoft.com/kb/810881 ""Access is Denied" Error Message When You Try to Open a Folder [Q810881]")  
 More Info [MS KB825751](http://support.microsoft.com/kb/825751 "HOW TO: Use Xcacls.vbs to Modify NTFS Permissions [Q825751]")  