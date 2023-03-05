---
title: 'Setting the default folder view for all folders'
date: '2008-06-14T16:22:53+02:00'
status: publish
permalink: /article/winnt-default-folder-view.html
author: Snakefoot
excerpt: 'How to configure the Windows Explorer to display all folders the same way.'
type: post
id: 766
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
To configure all folders to display the files the same way:

1. Use Windows Explorer to browse to a folder, and configure how the folder should appear (Set the wanted View - Details/List/Tiles/Thumbnails, Select columns, Change column order, Resize column width etc.).
2. In the Windows Explorer click the Tools-menu and select "Folder Options..."
3. Change to the "View"-fan and press "Reset Folders" and then press the "Apply to all folders"-button
 
 More Info [MSDN - New Windows XP Shell Features](http://msdn.microsoft.com/en-us/magazine/cc302214.aspx "MSDN Magazine November 2001 - New Graphical Interface: Enhance Your Programs with New Windows XP Shell Features")  
 More Info [MS KB812003](http://support.microsoft.com/kb/812003 "How to modify your folder view settings or to customize a folder")  
##### Changing the Folder Type template for a folder

 Even after having configured all folder to look the same way, then some folders may still display differently, because the Folder type has been configured. To configure the Folder Type of a folder:
1. Right click on the folder and select "Properties"
2. Select the "Customize"-fan and here can you configure "What kind of folder do you want?" by changing what Folder Type to use as template.  
    
   The different templates have different columns pre-configured and options available: 
  - Pictures(best for many files) - Introduces a Filmstrip mode in the Windows Explorer View-menu.
 
 Note Windows XP will automatically [cache folder customization](/article/winnt-custom-folder.html), so changes made to a single folder will be remembered when the folder is visited again.

##### Configure the default Folder Type template for all users

 If having dynamic / roaming users and want and want to configure the default Folder view for all users through the registry:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\ShellNoRoam \\Bags \\AllFolders \\Shell\]  
>  WFlags = 0  
>  Mode = 4  
>  vid = "{137E7700-3573-11CF-AE69-08002B2E1262}"

 Note the following table can be used to configure the above values (WFlags should always be 0) <table border="1"><tr><th>View</th><th>Mode</th><th>vid</th></tr><tr><td>Icons</td><td>1</td><td>{0057D0E0-3573-11CF-AE69-08002B2E1262}</td></tr><tr><td>List</td><td>3</td><td>{0E1FA5E0-3573-11CF-AE69-08002B2E1262}</td></tr><tr><td>Details</td><td>4</td><td>{137E7700-3573-11CF-AE69-08002B2E1262}</td></tr><tr><td>Thumbnail</td><td>5</td><td>{8BEBB290-52D0-11D0-B7F4-00C04FD706EC}</td></tr><tr><td>Tiles</td><td>6</td><td>{65F125E5-7BE1-4810-BA9D-D271C8432CE3}</td></tr><tr><td>Filmstrip</td><td>7</td><td>{8EEFA624-D1E9-445B-94B7-74FBCE2EA11A}</td></tr></table>

 Note if not wanting to show the status-bar in the default folder view:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\ShellNoRoam \\Bags \\AllFolders \\Shell\]  
>  Status = 0