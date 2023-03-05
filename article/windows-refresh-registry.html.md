---
title: 'Reload the registry by restarting Explorer.exe'
date: '2001-01-01T14:07:20+01:00'
status: publish
permalink: /article/windows-refresh-registry.html
author: Snakefoot
excerpt: 'How one can reload the HKEY\_CURRENT\_USER registry hive without needing a restart.'
type: post
id: 243
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - windows-explorer
post_format: []
tags:
    - windows-explorer
---
It is possible to refresh the HKEY\_CURRENT\_USER registry hive, which can be useful if wanting to test a registry tweak without needing to restart.

- Win9x/Me : 
  1. Press the keys CTRL+ALT+DEL to get a list of running processes.
  2. End all explorer.exe processes.
  3. When the last explorer processes is being ended it will prompt you to shutdown the whole machine press "Cancel" to this request.
  4. After a moment it will prompt you for closing down explorer.exe press "Ok"
  5. The Taskbar will disappear for a moment while explorer stops and starts again automatically.
- WinNT/2k/XP: 
  1. Press the keys CTRL+SHIFT+ESC to start the Task Manager.
  2. End all explorer processes so the Taskbar disappears.
  3. To start explorer again use the Task Manager again and go to the menu File -&gt; New Task (Run...)
  4. Type in "explorer" and press Ok to start it again.
 
 If you have Network installed you can also close it down by choosing "Log Off.." in the "Start Button", and then login as the same user as before. This will restart the Explorer and the registry will be reloaded.