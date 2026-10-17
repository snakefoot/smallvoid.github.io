---
title: 'Quick restart by holding down the shift-key'
date: '1999-12-31T19:40:20+01:00'
permalink: /article/win9x-quick-reboot.html
author: Snakefoot
excerpt: 'How to use the Shift-key on the keyboard to activate faster reboot.'
type: post
id: 105
categories:
    - windows-95_tips
    - windows-98_tips
    - windows-me_tips
tags:
    - reboot
    - restart
---
When installing programs you often get told in the end of the installation that it will have to reboot, which will lead to it booting from scratch. Instead choose "No" to the question about rebooting, and press the Start Button, and select "Shutdown...", and choose to "Restart Windows", and while holding the Shift-key down press "Ok".  
  
 Related [Quick shutdown in Windows 98](/article/win98-fast-reboot.html)  
  
 More Info <a href="https://www.bing.com/search?q=KB%20143272%20Q143272" rel="nofollow" title="How to Restart Windows Without Restarting the Computer [Q143272]">MS KB143272</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20186925%20Q186925" rel="nofollow" title="Restarting Computer While Holding Down SHIFT Key Hangs Windows [Q186925]">MS KB186925</a>  
  
 Note one can also create an icon that will reboot the machine when clicked. Make a shortcut with this target command line:

 > rundll32.exe shell32.dll,SHExitWindowsEx 2  
  
 Besides doing reboot(2) one can also use the following values:
- 0 = Logoff
- 1 = Shutdown
- 2 = Reboot
- 4 = Forced shutdown
- 5 = Power Off
 
</div> More Info <a href="https://www.bing.com/search?q=KB%20193624%20Q193624" rel="nofollow" title="Windows Remembers the Previous Shutdown Option [Q193624]">MS KB193624</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20234216%20Q234216" rel="nofollow" title="How to Exit Windows 98/Me Automatically Using a Batch File [Q234216]">MS KB234216</a>  