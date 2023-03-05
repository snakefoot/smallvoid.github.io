---
title: 'Remove Links-folder from Internet Explorer favorites'
date: '2005-02-19T00:34:21+01:00'
status: publish
permalink: /article/ie-links-folder.html
author: Snakefoot
excerpt: 'Deleting the Links folder from the Internet Explorer bookmarks.'
type: post
id: 320
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - favorites
post_format: []
tags:
    - favorites
---
Internet Explorer (IE) has a menu-item called **Favorites**, which is folder where one can store favorite websites. By default the folder includes several non-interesting websites, which can be deleted except one folder called **Links**. When IE starts it checks whether the **Links**-folder exists and if it has been deleted then it is re-created.  
  
 The easy way is just to hide the folder:

1. Start IE and browse into the **Favorites**-folder
2. Right-click the **Links**-folder and select **Properties**
3. Set the **Attributes** so it becomes **Hidden**
4. Press the **Ok**-button
 
 The hard way is to stop the folder from being re-created:
1. Open the registry and set this registry value to an empty string:
   > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Toolbar\]  
   > LinksFolderName = "" (Default value = "Links")
2. Start IE and browse into the **Favorites**-folder
3. Right-click the **Links**-folder and select **Delete**