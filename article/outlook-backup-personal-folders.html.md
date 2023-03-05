---
title: 'Backup and restore the Outlook Personal Folders file (PST)'
date: '2005-11-10T18:42:35+01:00'
status: publish
permalink: /article/outlook-backup-personal-folders.html
author: Snakefoot
excerpt: 'Outlook stores the addresses and emails in a PST file, which one can backup and restore.'
type: post
id: 262
category:
    - Outlook
tag:
    - backup
    - personal-folders
post_format: []
tags:
    - 'personal-folders,backup'
---
The personal folders file (.pst) contains all local Outlook folders, such as Calendar, Inbox, Contacts, Tasks, Sent Items, Outbox, Deleted Items, and user-created folders.  
  
 The simple way to backup/restore the .pst file is to use the [Personal Folders Backup](http://www.microsoft.com/downloads/details.aspx?familyid=8b081f3a-b7d0-4b16-b8af-5a6322f4fd01) utility.

##### Find the location of the .pst file to allow backup of the file:

1. With Outlook98 or Outlook2000, make sure you have View / Folders selected.
2. Right click on **Personal Folders** and select **Properties**.
3. Click on the **Advanced** button.
4. Under **Filename**, it will show the path and name of the current PST file.
 
 More info [MS KB184817](http://support.microsoft.com/kb/184817 "OL98: (IMO) How to Back Up, Restore, or Move Outlook Data [Q184817]")  
 More info [MS KB196492](http://support.microsoft.com/kb/196492 "OL2000: (IMO) How to Back Up, Restore, or Move Outlook Data [Q196492]")  
 More info [MS KB287070](http://support.microsoft.com/kb/287070 "How to back up, to restore, or to move Outlook 2002 data in Outlook 2002 [Q287070]")  
  
##### Change the default location of the .pst file:

1. Start Outlook.
2. On the File menu, click **Data File Management**.
3. Select the old .pst that longer should be used, and then click **Remove**.
4. Click **Add**, select **Personal Folders File (.pst)**, click OK, and then select the .pst file you want to use as the new primary file.
5. Click OK.
 
 More info [MS KB257831](http://support.microsoft.com/kb/257831 "How to move your personal folders file in Outlook 2000 that is installed in Internet Mail Only mode [Q257831]")  
 More info [MS KB291636](http://support.microsoft.com/kb/291636 "How to move your personal folders (.pst) file in Outlook 2002 [Q291636]")  
 More info [MS KB300593](http://support.microsoft.com/kb/300593 "OL2002: How to Move the Hotmail .PST Cache File [Q300593]")  
 More info [MS KB830336](http://support.microsoft.com/kb/830336 "The .pst file has a different format and folder size limit in Outlook 2003 [Q830336]")  
 More info [MS KB832925](http://support.microsoft.com/kb/832925 "How to configure the size limit for both (.pst) and (.ost) files in Outlook 2003 [Q832925]")  
  
##### Using the Inbox Repair tool to repair a broken .PST file:

1. Search for the file **scanpst.exe** (Usually found here drive:\\Program Files\\Common Files\\System\\Mapi\\1033\\scanpst.exe)
2. Run scanpst.exe and point it to the damaged .PST file and press **Start**.
3. When the scan is completed, check **Make a backup of scanned file before repairing** and press **Repair**.
 
 More info [MS KB197316](http://support.microsoft.com/kb/197316 "How to use the Inbox Repair Tool to recover messages in Outlook 2000 that is installed with Corporate and Workgroup option [Q197316]")  
 More info [MS KB287497](http://support.microsoft.com/kb/287497 "How to use the Inbox Repair Tools to recover e-mail messages in Outlook 2002 and Outlook 2003 [Q287497]")  
 More info [MS KB329910](http://support.microsoft.com/kb/329910 ""Outlook.pst can not be accessed - 0x80040116" error message when you start Outlook 2000 or open a personal folder file [Q329910]")  
  
 Credits [OneComputerGuy.com](http://onecomputerguy.com/)