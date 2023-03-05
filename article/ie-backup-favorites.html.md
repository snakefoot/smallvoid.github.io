---
title: 'Backup or restore Internet Explorer bookmarks'
date: '2002-04-06T01:00:00+02:00'
status: publish
permalink: /article/ie-backup-favorites.html
author: Snakefoot
excerpt: 'Internet Explorer favorites are stored as lnk shortcuts and can be exported and imported as HTML.'
type: post
id: 263
category:
    - 'Internet Explorer (IE5)'
tag:
    - backup
    - favorites
post_format: []
tags:
    - 'favorites,backup'
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
>  More Info [MS KB158787](http://support.microsoft.com/kb/158787 "How to Establish a Common Favorites Folder with Windows NT [Q158787]")  
>  More Info [MS KB167124](http://support.microsoft.com/kb/167124 "Favorites Entries Lost During Internet Explorer Installation [Q167124]")