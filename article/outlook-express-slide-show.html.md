---
title: 'Configure Outlook Express for slide show of pictures'
date: '2003-08-09T18:46:56+02:00'
status: publish
permalink: /article/outlook-express-slide-show.html
author: Snakefoot
excerpt: 'Outlook Express has can be used as a picture viewer.'
type: post
id: 335
category:
    - 'Outlook Express'
tag:
    - picture
    - slideshow
post_format: []
tags:
    - 'picture,slideshow'
---
There is a slideshow feature built into Outlook Express (OE) 4 and 5. By standard when images are attached, then OE both shows the images as attachment or if HTML mail show the image in their proper location, but OE also shows the images in a preview list in the bottom of the mail. To configure OE to show one picture at a time set this DWORD value:

> \[HKEY\_CURRENT\_USER \\Identities \\{GUID} \\Software \\Microsoft \\Outlook Express \\5.0\]  
>  Automatically Inline Images = 2 (0 = Don't preview, 1 = Preview List, 2 = Slide Show)  
>  Automatic Slide Show Delay = 2 (Seconds before changing)

 Note if having [disabled scripting in OE](/article/outlook-express-security-zone.html) for security measures then the slide show will not work.  
  
 Note OE 6 doesn't support the slide show feature, but it will react to not showing the preview list in the bottom of the mail (Only showing the files as attachments, or if HTML mail only showing the pictures in the intended position).  
  
 More info [MS KB234489](http://support.microsoft.com/kb/234489 "OLEXP: How to Disable the Picture Slide Show Feature in Outlook Express [Q234489]")  