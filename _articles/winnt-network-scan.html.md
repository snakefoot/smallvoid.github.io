---
title: 'Configure the scanning for network shares and printers'
date: '2003-06-09T21:41:28+02:00'
permalink: /article/winnt-network-scan.html
author: Snakefoot
excerpt: 'The network crawler will automatically create shortcuts to the network shares and printers found on the netwok in My Network Places.'
type: post
id: 413
categories:
    - windows-xp_file-sharing
tags:
    - network-places
---
There is a builtin scanner that crawls/scans/searches the network and any shares or printers discovered are automatically added to My Network Places or Printers and Faxes.  
  
 The scanner/crawler is started in the following situations:

- At startup
- When opening My Network Places
- When refreshing My Network Places by pressing F5
 
 The scanner is not started if one of the following conditions are true:
- If more than 10 computers are detected sharing folders (To be gentle on corporate networks)
- If using DUN or VPN connection
- If the scanner is disabled.
 
 The scanner saves its findings here (If more than 7 days old then they are deleted)
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Netcrawl \\Shares\]  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Netcrawl \\Printers\]

 To disable the automatic scanning:
1. Open **Control Panel**
2. Double click **Folder Options** (Inside the grouping **Appearance and Themes**)
3. Select the **View** tab
4. In the **Advanced Settings** list uncheck **Automatically search for network folders and printers**
 
 It is reflected with this DWORD value in the registry:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  NoNetCrawling = 1

 More Info <a href="https://www.bing.com/search?q=KB+276322+Q276322" rel="nofollow" title="How to Disable Net Crawl Functionality [Q276322]">MS KB276322</a> (WinMe)  
 More Info <a href="https://www.bing.com/search?q=KB+320138+Q320138" rel="nofollow" title="HOW TO: Disable Automatic Search for Network Printers and Folders in Windows XP [Q320138]">MS KB320138</a>  
  
 Related [Prevent share listing in My Network places](/article/winnt-recent-shares.html)  