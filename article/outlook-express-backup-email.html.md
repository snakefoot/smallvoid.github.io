---
title: 'Backup and restore Outlook Express emails'
date: '2002-05-18T18:11:37+02:00'
status: publish
permalink: /article/outlook-express-backup-email.html
author: Snakefoot
excerpt: 'Outlook Express stores the emails in DBX files, which one can backup and restore.'
type: post
id: 260
category:
    - 'Outlook Express'
tag:
    - backup
post_format: []
tags:
    - backup
---
##### Backup the emails in Outlook Express(OE) 5:

1. Select in the menu Tools-&gt;Options
2. Select the Maintenance-Tab
3. Press the "Store Folder..." button, it will show where the emails are saved 
  - It will also allow one to move the folder to a different location.
4. The store folder will contain several .DBX files (Both for mail and news), but usually Index.dbx and Outbox.dbx are the ones to backup (Unless using extra folders or subfolders within the Inbox or Outbox)
 
 Note before doing a backup of the Inbox.dbx and Outbox.dbx then it might be a good idea to clean up your mails as the files can become large:
- Check for mails with attachments like pictures, movies and programs
- Empty the "Delete Items" folder
- Compact your mail using Tools -&gt; Options -&gt; Maintenance-tab -&gt; Clean Up Now-button -&gt; Compact-button.

##### Restore the emails after a clean install in OE5:

1. Select in the menu Import-&gt;Messages...
2. Select in the list "Microsoft Outlook Express 5.0"
3. Select with radio button that you want to "Import mail from an OE5 store directory"
4. Use Browse to direct it to the store directory which contains the \*.DBX files
5. It will now import the emails and put them into its own OE store folder.

##### Share OE5 email folder between two Windows installations:

1. Make sure one is using the same Outlook Express version in both OS
2. Bootup into the one OS where the emails are now. Move the Store Folder to an accessible location for both OS
3. Bootup into the second OS, and import from the accessible location. Then move the Store Folder in that OS to the accessible location
 
 Note after a move there might still be leftover files at the original location, to find those files do a search for the filename "outbox.dbx" and "inbox.dbx".  
  
 More Info [MS KB230208](http://support.microsoft.com/kb/230208 "OLEXP: How to Back Up E-mail Messages in Outlook Express 5 [Q230208]")  
 More Info [MS KB270670](http://support.microsoft.com/kb/270670 "OLEXP: How to Back Up and Recover Outlook Express Data [Q270670]")  