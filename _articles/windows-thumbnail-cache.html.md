---
title: 'Configure the caching of thumbnails in thumbs.db'
date: '2004-08-05T00:24:38+02:00'
permalink: /article/windows-thumbnail-cache.html
author: Snakefoot
excerpt: 'Thumbnail View uses a cache to allow quicker viewing of folders with pictures, and one can change the quality of these thumbnails.'
type: post
id: 306
categories:
    - windows-xp_tips
    - windows-2000_tips
    - windows-2003_tips
    - windows-98_tips
    - windows-me_tips
tags:
    - desktop
    - windows-explorer
    - picture
    - thumbnail
    - thumbnail-cache
---
The Thumbnail view was introduced with Windows 98 and allows one to easily overview a collection of pictures. This done by displaying a smaller version of the original image so it is possible to see several pictures on single screen. To optimize the thumbnail view a cache (Thumbs.db / ehThumbs.db) is made so all the pictures doesn't have to processed every time viewing the folder.  
  
 It is possible to configure thumbnails quality (Will also affect the size of the cache):

> \[HKEY\_CURRENT\_USER\\ Software\\ Microsoft \\ Windows\\ CurrentVersion\\ Explorer\]  
>  ThumbnailSize = 96 (Default, 96, Range 32-256)  
>   
>  \[HKEY\_CURRENT\_USER\\ Software\\ Microsoft \\ Windows\\ CurrentVersion\\ Explorer\]  
>  ThumbnailQuality = 90 (Default = 90, Range 50-100)  
>   
>  More Info [MS Technet](http://www.microsoft.com/technet/prodtechnol/winxppro/tips/default.mspx "Tips and Tricks for Windows XP Professional")  
>  More Info [MS Press: XP Registry Guide](http://www.microsoft.com/mspress/books/sampchap/6232.asp "Microsoft Windows XP Registry Guide")

 Note in Windows 98/Me/2000/XP the thumbnail view depends on these DLLs, and if unregistered the thumbnail view is disabled:
 > regsvr32 /u shimgvw.dll  
 > regsvr32 /u thumbvw.dll  
 >   
 >  More Info <a href="https://www.bing.com/search?q=KB%20272969%20Q272969" rel="nofollow" title="A Description of the Image Preview Feature [Q272969]">MS KB272969</a>

 Note in Windows XP the thumbnail cache can be disabled completely with this DWORD registry key:
 > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
 >  DisableThumbnailCache = 1 (Same as "Do not cache thumbnails" in Folder options)

 Note in Windows XP the thumbnail cache (and the thumbnail view) can be disabled for network-drives and -shares with this DWORD registry key:
 > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Policies\]  
 >  NoDetailsThumbnailOnNetwork = 1  
 >   
 >  More Info <a href="https://www.bing.com/search?q=KB%20830903%20Q830903" rel="nofollow" title="A file in a network folder opens as read-only or returns an error message that the file type cannot be recognized">MS KB830903</a>

 Note in Windows XP when holding down the SHIFT key while opening a folder in thumbnail view, then the picture titles and filenames will not be displayed and will give more room for the thumb nails.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20176882%20Q176882" rel="nofollow" title="How to Enable the Thumbnail View for Folders in Windows Explorer [Q176882]">MS KB176882</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20192573%20Q192573" rel="nofollow" title="Image Previews Not Displayed in Windows Explorer [Q192573]">MS KB192573</a>  
  
 Credits [Tlab404.com](http://tlab404.com/)