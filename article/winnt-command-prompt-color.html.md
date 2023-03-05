---
title: 'Change the color of the command prompt'
date: '2001-01-01T13:40:06+01:00'
status: publish
permalink: /article/winnt-command-prompt-color.html
author: Snakefoot
excerpt: 'How to change the text color and background color in the command prompt.'
type: post
id: 24
category:
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
tag:
    - visual-style
post_format: []
tags:
    - visual-style
---
If an old ANSI.SYS color fan then this might bring some joy, as one can colorize the command prompt console by changing the foreground and background color.  
  
 Edit the registry and add/update this setting (REG\_DWORD):

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Command Processor\]  
>  DefaultColor = 0A (Black background=0 with green text=A)

 Colour codes available: <table border="1" style="text-align:center;background:#AAAAAA"><tr><th>Code (Hex)</th><th>Color</th></tr><tr><td>0</td><td><span style="color:#000000">black</span></td></tr><tr><td>1</td><td><span style="color:#0000A0">blue</span></td></tr><tr><td>2</td><td><span style="color:#006A35">green</span></td></tr><tr><td>3</td><td><span style="color:#00FFFF">cyan</span></td></tr><tr><td>4</td><td><span style="color:#D20000">red</span></td></tr><tr><td>5</td><td><span style="color:#FF00FF">magenta</span></td></tr><tr><td>6</td><td><span style="color:#D56A00">yellow/brown</span></td></tr><tr><td>7</td><td><span style="color:#FFFFFF">white</span></td></tr><tr><td>8</td><td><span style="color:#808080">gray</span></td></tr><tr><td>9</td><td><span style="color:#0000FF">bright blue</span></td></tr><tr><td>A</td><td><span style="color:#00FF00">bright green</span></td></tr><tr><td>B</td><td><span style="color:#D9FFFF">bright cyan</span></td></tr><tr><td>C</td><td><span style="color:#FF2F2F">bright red</span></td></tr><tr><td>D</td><td><span style="color:#FF9FFF">bright magenta</span></td></tr><tr><td>E</td><td><span style="color:#FBFB00">bright yellow</span></td></tr><tr><td>F</td><td><span style="color:#FFFFFF">white</span></td></tr></table>

 Note one can also use the program "COLOR" from the command prompt to change the color. > COLOR 0A

 Note one can also select properties for a shortcut to the cmd.exe, and select "Properties" and change the colors in the fan "Colors".