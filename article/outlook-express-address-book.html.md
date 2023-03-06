---
title: 'Backup and restore Outlook Express Address Book'
date: '2002-05-18T18:28:31+02:00'
status: publish
permalink: /article/outlook-express-address-book.html
author: Snakefoot
excerpt: 'Outlook Express Address Book stores the addresses in a WAB file, which one can backup and restore.'
type: post
id: 261
category:
    - 'Outlook Express'
tag:
    - address-book
    - backup
post_format: []
tags:
    - 'address-book,backup'
---
##### Backup email addresses in Outlook Express(OE) 5:

1. In the OE menu go to Tools-&gt;Address Book...
2. In the Address Book window go to the menu File-&gt;Export-&gt;Address Book (WAB).
3. Browse to find a location you want, and save the WAB file which will contain the addresses.

##### Restore email addresses in OE5:

1. In the OE menu go to Tools-&gt;Address Book...
2. In the Address Book window go to the menu File-&gt;Import-&gt;Address Book (WAB).
3. Browse and select the WAB file containing the addresses.

##### The location of the address book file in OE5:

1. In the OE menu go to Tools-&gt;Address Book...
2. In the Address Book window go to menu Help-&gt;About.
3. The popup should show where the wab file is stored.

##### Change the location of the address book file in OE5:

1. Find where your address book file is saved.
2. Close down OE and the Address Book.
3. Copy the address book file to the wanted location.
4. Start regedit and go to this location:  
    
  > \[HKEY\_CURRENT\_USER\\ Software\\ Microsoft\\ WAB\\ WAB4\\ Wab File Name\]
5. Double click the (Default) entry and change it to the wanted location.
 
 More Info [MS KB270670](http://support.microsoft.com/kb/270670 "OLEXP: How to Back Up and Recover Outlook Express Data [Q270670]")  
 More Info [MS KB156828](http://support.microsoft.com/kb/156828 "How to Change the Location of the Windows Address Book [Q156828]")  
##### Sharing contacts between Outlook Express and Outlook:

 It is possible to make Outlook Express uses the Outlook Contact folder as Address Book instead of the WAB file. The Outlook contacts are stored in the [.PST file](/article/outlook-backup-personal-folders.html).
> \[HKEY\_CURRENT\_USER \\SOFTWARE \\Microsoft \\Wab \\Wab4\]  
>  UseOutlook = 1 (1 = Outlook Express will start Outlook and use its Contact folder)  
>   
>  More Info [MS KB269777](http://support.microsoft.com/kb/269777 "OLEXP: Error Message: Address Book Failed to Load [Q269777]")

 Credits [tomsterdam.com](http://tomsterdam.com/)