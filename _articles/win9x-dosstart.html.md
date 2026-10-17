---
title: 'Using DosStart.bat to configure DOS when leaving Windows'
date: '2000-01-01T00:20:32+01:00'
permalink: /article/win9x-dosstart.html
author: Snakefoot
excerpt: 'Load DOS drivers when leaving Windows, instead of loading them before Windows starts.'
type: post
id: 160
categories:
    - windows-95_tips
    - windows-98_tips
tags: []
---
When performing an exit to DOS, by pressing the **Start**-button and selects the **Shutdown...**-option to **Restart the computer in MS-DOS mode**, then it checks the properties of a special file called **Exit to DOS.pif**:

- By the default the properties are set to **Use Current MS-DOS Configuration**, and it will exit Windows and execute **DosStart.bat** (In the Windows folder)
- If the properties are set to **Specify A New MS-DOS Configuration**, then it will use the Autoexec.bat and Config.sys specified by **Exit to DOS.pif**
 
 The [batch file](/article/batch-file.html) DosStart.bat can be used to contain all the drivers and settings which usually resides in Autoexec.bat and Config.sys. CD-Rom drivers and other device drivers can be loaded by using the utility [Dynaload](/article/dynaload.html). It will make the Windows startup faster when only loading DOS drivers at Windows exit.  
  
 More Info <a href="https://www.bing.com/search?q=KB+134400+Q134400" rel="nofollow" title="General Tips for Using MS-DOS Mode [Q134400]">MS KB134400</a>  
 More Info <a href="https://www.bing.com/search?q=KB+135174+Q135174" rel="nofollow" title="Cannot Access CD-ROM Drive from MS-DOS Mode or Command Prompt [Q135174]">MS KB135174</a>  
 More Info <a href="https://www.bing.com/search?q=KB+138996+Q138996" rel="nofollow" title="Description of Restarting Computer in MS-DOS Mode [Q138996]">MS KB138996</a>  
 More Info <a href="https://www.bing.com/search?q=KB+141308+Q141308" rel="nofollow" title="How to Run Automatic Commands When Starting in MS-DOS Mode [Q141308]">MS KB141308</a>  