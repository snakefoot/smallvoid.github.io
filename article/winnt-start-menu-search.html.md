---
title: 'Faster start menu search by not searching all files'
date: '2007-07-02T07:44:52+02:00'
status: publish
permalink: /article/winnt-start-menu-search.html
author: Snakefoot
excerpt: 'The start menu search in Windows Vista will by default search all folders and files in My Documents folder.'
type: post
id: 648
category:
    - Desktop
tag:
    - desktop-search
    - file-search
post_format: []
tags:
    - 'desktop-search,file-search'
---
Windows Vista start-menu has the ability to search for start menu items. This is a lot faster than browsing through the different folders in the start-menu. By default it will search through many different locations to find files/documents that matches your search, which can slow down the search.  
  
 Right click the Start-button and select **Properties** and on the **Start Menu**-tab click the **Customize**-button.

- **Search Communications** - Should it search Windows Mail and Windows Contacts (Default - On)
- **Search Favorites and History** - Should it search Internet Explorer bookmarks and visited web-sites (Default - On)
- **Search Files** - If having many files in the My Documents folder consider changing it to "Don't search for files" (Default - Search this user's files)

##### Use keyword to launch application

 Example if wanting to launch firefox, by just entering "ff", then just create a shortcut in the Start-menu named ff that points to the Firefox application.  
  
 A more difficult approach is to register a pseudo application called "ff.exe" in the registry:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\App Paths **\\ff.exe**\]  
>  (Default) = "C:\\Firefox\\Firefox.exe"

 Credits [Lockergnome.com](http://www.lockergnome.com/)