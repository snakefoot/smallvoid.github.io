---
title: 'Quick restart by holding down the shift-key'
date: '1999-12-31T19:40:20+01:00'
status: publish
permalink: /article/win9x-quick-reboot.html
author: Snakefoot
excerpt: 'How to use the Shift-key on the keyboard to activate faster reboot.'
type: post
id: 105
category:
    - Tips
    - Tips
    - Tips
tag:
    - reboot
    - restart
post_format: []
tags:
    - 'reboot,restart'
---
When installing programs you often get told in the end of the installation that it will have to reboot, which will lead to it booting from scratch. Instead choose "No" to the question about rebooting, and press the Start Button, and select "Shutdown...", and choose to "Restart Windows", and while holding the Shift-key down press "Ok".  
  
 Related [Quick shutdown in Windows 98](/article/win98-fast-reboot.html)  
  
 More Info [MS KB143272](http://support.microsoft.com/kb/143272 "How to Restart Windows Without Restarting the Computer [Q143272]")  
 More Info [MS KB186925](http://support.microsoft.com/kb/186925 "Restarting Computer While Holding Down SHIFT Key Hangs Windows [Q186925]")  
  
 Note one can also create an icon that will reboot the machine when clicked. Make a shortcut with this target command line:

 > rundll32.exe shell32.dll,SHExitWindowsEx 2  
  
 Besides doing reboot(2) one can also use the following values:
- 0 = Logoff
- 1 = Shutdown
- 2 = Reboot
- 4 = Forced shutdown
- 5 = Power Off
 
</div> More Info [MS KB193624](http://support.microsoft.com/kb/193624 "Windows Remembers the Previous Shutdown Option [Q193624]")  
 More Info [MS KB234216](http://support.microsoft.com/kb/234216 "How to Exit Windows 98/Me Automatically Using a Batch File [Q234216]")  