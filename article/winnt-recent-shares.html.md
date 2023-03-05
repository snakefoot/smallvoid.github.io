---
title: 'Remove listing of recent shares in My Network places'
date: '2002-10-28T21:34:40+01:00'
status: publish
permalink: /article/winnt-recent-shares.html
author: Snakefoot
excerpt: 'Shortcuts to network shares visited will automatically be added to My Network Places.'
type: post
id: 412
category:
    - Desktop
    - Desktop
    - Desktop
tag:
    - network-places
post_format: []
tags:
    - network-places
---
In Win2k/XP when you visit shares then they get listed in "My Network Places".  
  
 In Win2k one can prevent this behavior by changing the following user policy:

1. Run the program MMC using "Start Button" -&gt; "Run..."
2. In the program menu select "Console" -&gt; "Add/Remove Snap in"
3. Press the button "Add" and select "Group Policy" and press "Ok"
4. In the Console Window go to this folder "Local Computer Policy" -&gt; "User Configuration" -&gt; "Administrative Templates" -&gt; "Desktop"
5. Go to the entry "Do not add shares of recently opened documents to My Network Places" and double click it and set to "Enabled"
 
 In WinXP one can prevent this behavior by changing the following user policy:
1. Run Gpedit.msc using "Start Button" -&gt; "Run..."
2. In the Console Window go to this folder "User Configuration" -&gt; "Administrative Templates" -&gt; "Start Menu and Taskbar"
3. Go to the entry "Do not add shares of recently used documents to Network Places" and double click it and set to "Enabled"
 
 It is the same as setting this DWORD registry key :  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoRecentDocsNetHood = 1 (Default = 0)

 Note after disabling this feature then the list of old share-shortcuts has to be manually cleared one last time.  
  
 Related [Configure the scanning for shares and printers in WinXP](/article/winnt-network-scan.html)