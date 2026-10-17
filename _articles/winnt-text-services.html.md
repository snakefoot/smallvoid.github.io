---
title: 'Disable speech recognition to free resources'
date: '2004-05-10T01:25:37+02:00'
permalink: /article/winnt-text-services.html
author: Snakefoot
excerpt: 'Windows includes text services to handle speech and handwritting recognition that can cause conflicts with other applications.'
type: post
id: 377
categories:
    - windows-xp_performance
tags:
    - handwriting-recognition
    - ms-office
    - speech-recognition
---
It is possible to control applications through a speech interface, which can be conveniently for some. Microsoft have included this feature in Windows XP along with Office XP/2003, but if you don't use this feature then it is recommended to disable it. The speech recognition needs to make hooks into all applications to forward the commands from the speech interface to the applications, and many times this causes conflicts with the applications.  
  
 To disable the builtin speech recognition (Sapisvr.exe/ctfmon.exe) in Windows XP:

- Press **Start**-button, **Settings** and open **Control Panel**
- Double click **Date, Time, Language, and Regional Options**
- Choose the **Languages**-tab and click **Details** in the **Text services and input languages**-box
- Click the **Language Bar** in the **Preferences**-box
- Unchek the **Extend support of advanced text services to all programs**-box
- Check the **Turn off advanced text services**-box
- This should be reflected with these registry entries:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\CTF\]  
  >  Disable Thread Input Manager = 1  
  >   
  >  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\CTF \\Langbar\]  
  >  ExtraIconsOnMinimized = 0  
  >  ShowStatus = 2  
  >   
  >  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\CTF \\MSUTB\]  
  >  ShowDeskBand = 1
 
 More Info <a href="https://www.bing.com/search?q=KB%20313176%20Q313176" rel="nofollow" title="Programs May Start, Quit, Lose, and Gain Focus Randomly [Q313176]">MS KB313176</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20316215%20Q316215" rel="nofollow" title="PRB: Internet Explorer Stops Responding and Other System Performance Issues [Q316215]">MS KB316215</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20316768%20Q316768" rel="nofollow" title="OFFXP: Computer Runs Slowly When You Use Handwriting Recognition and Speech Recognition Components [Q316768]">MS KB316768</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20827323%20Q827323" rel="nofollow" title="How to turn off the Office XP Language Bar [Q827323]">MS KB827323</a>  
  
 To uninstall speech recognition (ctfmon.exe) from MS Office (All Windows versions):
- Quit all Office programs
- Press **Start**-button, **Settings** and open **Control Panel**
- In the Control Panel double click **Add/Remove Programs**-applet
- On the **Install/Uninstall**-tab and select **Microsoft Office ???? Product** and press **Add/Remove**
- In the **Maintenance Mode Options**-dialog choose **Add or Remove Features** and click **Next**
- In the **Choose installation options for all Office applications and tools**-dialog expand **Office Shared Features**
- Set **Alternative User Input** to **Not Available** and click **Update**
 
 More Info <a href="https://www.bing.com/search?q=KB%20282599%20Q282599" rel="nofollow" title="OFFXP: What Is CTFMON and What Does It Do? [Q282599]">MS KB282599</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20326526%20Q326526" rel="nofollow" title="HOW TO: Turn Off the Speech Recognition and Handwriting Recognition Features in Office XP [Q326526]">MS KB326526</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20823586%20Q823586" rel="nofollow" title="HOW TO: Turn Off the Speech Recognition and Handwriting Recognition Features in Office 2003 [Q823586]">MS KB823586</a>  