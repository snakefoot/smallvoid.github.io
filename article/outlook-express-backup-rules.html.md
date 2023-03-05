---
title: 'Backup and restore Outlook Express message rules'
date: '2002-05-18T18:27:33+02:00'
status: publish
permalink: /article/outlook-express-backup-rules.html
author: Snakefoot
excerpt: 'Outlook Express message rules are stored in the Windows registry, which one can backup and restore.'
type: post
id: 331
category:
    - 'Outlook Express'
tag:
    - backup
    - message-rules
post_format: []
tags:
    - 'message-rules,backup'
---
To backup your rules in Outlook Express(OE) 5 you have to use regedit :

1. Start regedit
2. Locate following registry entry and export it:
> \[HKEY\_CURRENT\_USER \\Identities \\{GUID} \\Software \\Microsoft \\Outlook Express \\5.0 \\Block Senders\]
3. Locate following registry entry and export it:
> \[HKEY\_CURRENT\_USER \\Identities \\{GUID} \\Software \\Microsoft \\Outlook Express \\5.0 \\Rules \\Mail\]
 
 To restore your rules in OE, you have to use notepad and regedit :  
1. Start regedit
2. Locate following registry entry:
> \[HKEY\_CURRENT\_USER \\Identities \\{GUID}\]  
>  UserId = {GUID}
3. Double click the UserId and save the value to clipboard (CTRL+C)
4. Open each of the exported registry files with notepad and replace the old { Identity Number } with the new one (Saved in Clipboard).
5. Save the now changed exported registry files.
6. Import the exported registry files
 
 Related [Take advantage of message rules in Outlook Express](/article/outlook-express-message-rules.html)  
  
 More Info [MS KB181084](http://support.microsoft.com/kb/181084 "OLEXP: How to Back Up Your Inbox Assistant Rules in Outlook Express [Q181084]")  
 More Info [MS KB276511](http://support.microsoft.com/kb/276511 "OLEXP: How to Backup and Restore Outlook Express Blocked Senders List and Other Mail Rules [Q276511]")  