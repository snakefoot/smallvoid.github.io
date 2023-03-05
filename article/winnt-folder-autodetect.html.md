---
title: 'Configure automatic detection of folder type'
date: '2007-11-16T21:25:59+01:00'
status: publish
permalink: /article/winnt-folder-autodetect.html
author: Snakefoot
excerpt: 'Windows Explorer tries to guess how to display a directory, by looking at the files within.'
type: post
id: 759
category:
    - Desktop
tag:
    - custom-folders
    - visual-style
    - windows-explorer
post_format: []
tags:
    - 'windows-explorer,custom-folders,visual-style'
---
Windows Explorer can display files using different view types, depending on the files being pictures, music, movies etc. When opening a folder using Windows Explorer, then it tries to guess the folder type so the contents gets displayed properly.

- Looks in the [cache of customized folders](#cache) to see if there is a saved view for the folder.
- Looks through the parent folders to see any of them specifies that sub folders should inherit their view.
- Looks in the registry checks if the "AllFolders" value specifies a default view template.
- Looks at the files in the folder and tries to guess what folder type it is. After having guessed the folder type, then it checks if there is any default view-template for the folder-type. 
  - To update the default view-template for a detected folder-type, then open a folder of that folder-type and customize it. To use it as default when no saved view-template is found, open Folder Options and press the "Apply to Folders"-buttons (Will only update the default view-template for that folder-type)
 
 This is very nice as one always can tell Windows Explorer to use a different view template in case it should guess wrong, and it will remember it as a saved view. The problem comes when the saved view expires in the cache, or if one doesn't like Windows Explorer to display the files differently depending on the type of files.  
##### Set default folder view for all folders

 If setting the "AllFolders" registry key, then it will prevent Windows Explorer from guessing the folder type and applying the associated view template:
1. Click on the **Start** menu and choose **Computer**.
2. In the **Tools** menu click **Folder options...**.
3. Click the **View**-tab and press the **Reset Folders** button.
4. Open the registry editor and create the following registry value:
  > \[HKEY\_CURRENT\_USER \\Software \\Classes \\Local Settings \\Software \\Microsoft \\Windows \\Shell \\Bags \\AllFolders \\Shell\]  
  >  FolderType = "NotSpecified"  
  >   
  >  There are other view templates one can specify as default:
  > 
  > 
  > - Contacts
  > - Music
  > - MusicIcons
  > - Documents
  > - Pictures
 
<a name="cache"></a>
##### Caching of customized folders

 Windows Vista automatically remembers the chosen appearance of each folder, when the user browses through the folders. By default the cache is limited to 5000 folders:
> \[HKEY\_CURRENT\_USER \\Software \\Classes \\LocalSettings \\Software \\Microsoft \\Windows \\Shell\]  
>  BagMRU Size = 5000 (Number of local folders to remember)  
>   
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\Shell\]  
>  BagMRU Size = 400 (Number of network folders to remember)

 The cache is stored in the registry database at this location:
> \[HKEY\_CURRENT\_USER \\Software \\Classes \\LocalSettings \\Software \\Microsoft \\Windows \\Shell \\Bags\]  
> \[HKEY\_CURRENT\_USER \\Software \\Classes \\LocalSettings \\Software \\Microsoft \\Windows \\Shell \\BagMRU\]  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\Shell \\Bags\]  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\Shell \\BagMRU\]

 Credits [VistaX64.com](http://www.vistax64.com/)