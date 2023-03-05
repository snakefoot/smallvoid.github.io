---
title: 'Configure the caching of customized folders'
date: '2003-01-10T20:23:51+01:00'
status: publish
permalink: /article/winnt-custom-folder.html
author: Snakefoot
excerpt: 'Configure how many folder customizations Windows should remember.'
type: post
id: 404
category:
    - Desktop
tag:
    - custom-folders
    - windows-explorer
post_format: []
tags:
    - 'windows-explorer,custom-folders'
---
Windows XP automatically caches the chosen appearance of each folder, when the user browses through the folders. One can configure for how many local (ShellNoRoam) and network folders it will remember the customization with these DWORD values:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\Shell\]  
>  BagMRU Size = 5000 (Default - 5000, XP SP1 - 200)  
>   
>  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\ShellNoRoam\]  
>  BagMRU Size = 5000 (Default - 5000, XP SP1 - 200)

 One can clear the customization of all folders by deleting the following subkeys (Sometimes necessary if Windows stops remembering ones customizations):
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\Shell \\Bags\]  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\Shell \\BagMRU\]  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\ShellNoRoam \\Bags\]  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\ShellNoRoam \\BagMRU\]

 Note to enable Custom folders one have enable the following option: Control Panel -&gt; Folder Options -&gt; "Remember each folder's view settings". It should be reflected in this DWORD registry value:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  ClassicViewState = 0 (0 = Remember Folder View, 1 = Don't remember)

 More Info [MS KB812003](http://support.microsoft.com/kb/812003 "How to modify your folder view settings or to customize a folder [Q812003]")  
 More Info [MS KB813711](http://support.microsoft.com/kb/813711 "Your view settings or customizations for a folder are lost or incorrect [Q813711]")  
  
 Related [Setting the default folder view for all folders](/article/winnt-default-folder-view.html)  
 Related [Configure caching of remote customized folders in WinXP](/article/winnt-custom-folder-cache.html)  
  
 Credits [ntfaq.com](http://ntfaq.com/)