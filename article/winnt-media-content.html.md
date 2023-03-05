---
title: 'Configuring the media preview in Windows Explorer'
date: '2003-05-25T21:07:26+02:00'
status: publish
permalink: /article/winnt-media-content.html
author: Snakefoot
excerpt: 'Change whether it should extract file details for media files and display thumbnail preview.'
type: post
id: 410
category:
    - Desktop
tag:
    - thumbnail
    - windows-media-player
post_format: []
tags:
    - 'thumbnail,windows-media-player'
---
Microsoft has extended the ability of the Explorer to also act as a picture viewer, music player and media player. These user friendly media shell extensions can be nice if NOT using the Classic desktop, but they also introduce some side effects (Even if using Classic desktop):

- Uses longer time to show the contents of a folder because it extracts the details of all media files within the folder (Ex. if having a folder with MP3 files).
- The scanning of files causes the files to be locked by the Explorer, and so when trying to delete the file one will get an error:
  > *Cannot delete/move &lt;filename&gt;: It is being used by another process or program. Close any programs that might be using the file and try again*
- The scanning of files causes high CPU usage, if having a "faulty" file. (F.ex. a large AVI/MPG/MPEG file where the index is broken will make Windows Explorer to scan the entire file).
 
 One can [Disable the preview/thumbnails-view entirely (Thumbs.db)](/article/windows-thumbnail-cache.html)  
  
 One can disable the extraction of media file properties entirely (WinXP+):
 > regsvr32 /u shmedia.dll

 One can disable the extraction of media file properties for certain files (WinXP+):
> \[HKEY\_CLASSES\_ROOT \\SystemFileAssociations \\**.avi** \\shellex \\PropertyHandler\]  
> **(Default)** = (Value not set)  
>   
>  Note to disable select the **(Default)**-value and press Delete-key, and it will change to "(Value not set)".  
>  To disable preview for other file-types just exchange the **.avi** with the wanted filetype and delete the **(Default)** for the wanted file-type.  
>   
>  More Info [MS KB822430](http://support.microsoft.com/kb/822430 "Windows Stops Responding When You Click a Large AVI File in Windows Explorer [Q822430]")

 Note if one likes the shell extensions, but just having problems deleting a file then try one of these:
- Download and install [Unlocker](/article/winnt-unlocker.html), which can close the handles created to the file, so one is not blocked from deleting it
- Rename the file so it no longer has the extension of a media file
- Momentarily unregister shmedia.dll (Media File Property Extractor Shell Extension) to delete the file (WinXP+):
  > regsvr32 /u shmedia.dll  
  >  (delete the file)  
  >  regsvr32 shmedia.dll
- Close all explorer.exe and use the command-prompt.
- Boot in safemode and delete the file, as the preview feature is disabled.
 
 Related [Configure compressed folders in Windows Explorer](/article/windows-compressed-folders.html)  
 Related [Change Webview for all folders to stop movie preview](/article/windows-web-content.html)  
  
 Credits [TweakXp.com](http://tweakxp.com/)