---
title: 'Change the color of Blue Screen of Death (BSOD)'
date: '2000-01-01T01:43:16+01:00'
status: publish
permalink: /article/bsod-change-color.html
author: Snakefoot
excerpt: 'How to change the color of the BSOD to make it easier to read or just for fun.'
type: post
id: 135
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - blue-screen-of-death
    - visual-style
post_format: []
tags:
    - 'blue-screen-of-death,visual-style'
---
If visually impaired, then the Blue Screen of Death (BSOD) can be difficult to read with its white text on blue background. It is possible to change the color of the BSOD by adding these lines to the **386enh**-section of the **System.ini**-file in the Windows-folder:

> \[386enh\]  
>  ;COMMENT The following 2 lines makes the screen black and the text white  
>  MessageBackColor=0  
>  MessageTextColor=7

 Color codes available: <table border="1" style="text-align:center;background:#AAAAAA"><tr><th>Code (Hex)</th><th>Color</th></tr><tr><td>0</td><td><span style="color:#000000">black</span></td></tr><tr><td>1</td><td><span style="color:#0000A0">blue</span></td></tr><tr><td>2</td><td><span style="color:#006A35">green</span></td></tr><tr><td>3</td><td><span style="color:#00FFFF">cyan</span></td></tr><tr><td>4</td><td><span style="color:#D20000">red</span></td></tr><tr><td>5</td><td><span style="color:#FF00FF">magenta</span></td></tr><tr><td>6</td><td><span style="color:#D56A00">yellow/brown</span></td></tr><tr><td>7</td><td><span style="color:#FFFFFF">white</span></td></tr><tr><td>8</td><td><span style="color:#808080">gray</span></td></tr><tr><td>9</td><td><span style="color:#0000FF">bright blue</span></td></tr><tr><td>A</td><td><span style="color:#00FF00">bright green</span></td></tr><tr><td>B</td><td><span style="color:#D9FFFF">bright cyan</span></td></tr><tr><td>C</td><td><span style="color:#FF2F2F">bright red</span></td></tr><tr><td>D</td><td><span style="color:#FF9FFF">bright magenta</span></td></tr><tr><td>E</td><td><span style="color:#FBFB00">bright yellow</span></td></tr><tr><td>F</td><td><span style="color:#FFFFFF">white</span></td></tr></table>

 More Info [MS KB90740](http://support.microsoft.com/kb/90740 "Color Values for MessageBackColor and MessageTextColor Setting [Q90740]")  