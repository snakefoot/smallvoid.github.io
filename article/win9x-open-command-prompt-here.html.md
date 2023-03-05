---
title: 'Open DOS Command Prompt Here'
date: '2006-02-16T01:08:53+01:00'
status: publish
permalink: /article/win9x-open-command-prompt-here.html
author: Snakefoot
excerpt: 'Extend the right-click context-menu of a folder to open a DOS command prompt.'
type: post
id: 120
category:
    - Tips
    - Tips
    - Tips
tag:
    - 'Command Prompt'
    - context-menu
    - windows-explorer
post_format: []
tags:
    - 'context-menu,windows-explorer,command-prompt'
---
If you want to open a command prompt anywhere without manually needing to move to the right directory. Just need to right click the directory.

1. Start "My Computer"
2. In the "My Computer" menu select "Tools" -&gt; "Folder Options..."
3. Select the fan "File Types"
4. Sort the registered file types by name by clicking the 2nd column
5. Find and select the file type "Folder"
6. Press the "Edit" button, and a new window pops up ("Advanced" if using WinMe)
7. Press the "New..." button, and a new window pops up
8. Set the action to be:
   > Open Command Prompt Here
9. Set the application to be:
   > C:\\Windows\\command.com /k doskey cd "%1"
10. Press Ok to save the newly added entry
 
 Now when one right clicks a directory, one is given the option to open a command prompt. This can also be done with the [Win95 Powertoys](/article/win95-power-toys.html) (Though it doesn't activate doskey).  
  
 Related [Configure file types to include your own useful actions](/article/explorer-context-menu.html)