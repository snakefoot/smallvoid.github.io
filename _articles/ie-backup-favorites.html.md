---
title: 'Backup or restore Internet Explorer bookmarks'
date: '2002-04-06T01:00:00+02:00'
permalink: /article/ie-backup-favorites.html
author: Snakefoot
excerpt: 'Internet Explorer favorites are stored as lnk shortcuts and can be exported and imported as HTML.'
type: post
id: 263
categories:
    - web-browser_internet-explorer-ie5
tags:
    - backup
    - favorites
---
To backup the favorite bookmarks in Internet Explorer(IE) 5:

1. Start IE and in the menu **File** select the item **Import and Export...**
2. Select to **Export Favorites**
3. Select what folder(Includes subfolders) to export
4. Select **Export to a File or Address** and select a location where to save the HTML file which will contain the favorites
 
 To restore the favorite bookmarks in IE5:
1. Start IE and in the menu **File** select the item **Import and Export...**
2. Select to **Import Favorites**
3. Select **Import from a File or Address** and browse to the location with the HTML file which contains the favorites.
 
 To see/change the location of the Favorites Folder (Easier to use Tweak UI):
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Shell Folders\]  
>  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\User Shell folders\]  
>  Favorites = "C:\\Windows\\Favorites"  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+158787+Q158787" rel="nofollow" title="How to Establish a Common Favorites Folder with Windows NT [Q158787]">MS KB158787</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+167124+Q167124" rel="nofollow" title="Favorites Entries Lost During Internet Explorer Installation [Q167124]">MS KB167124</a>