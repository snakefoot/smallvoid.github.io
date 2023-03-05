---
title: 'Make screendump of the desktop using Print Screen'
date: '2001-01-01T11:35:19+01:00'
status: publish
permalink: /article/windows-screen-dump.html
author: Snakefoot
excerpt: 'How to use the keyboard key "Print Screen" to make a screen dump.'
type: post
id: 237
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - screendump
post_format: []
tags:
    - screendump
---
Windows can take a screenshot, when using one of the following keyboard shortcuts:

- Print Screen (Prt Scr) - Will take a screenshot of the entire desktop and save to clipboard
- Alt + Print Screen (PrtScr) - Will a screenshot of the active window and save to clipboard
- Win + Print Screen (PrtScr) - Will take a screenshot of the entire desktop and save as PNG (Win8+)
 
 To see/edit the content of the clipboard open MsPaint and do a Paste, and now you are able to edit the screendump and later save it into a file.  
  
 Note if wanting to make screenshots for documentation or bug reports, then one should consider to use advanced tools that allows one to annodate and crop the screenshots:
- [GreenShot](http://sourceforge.net/projects/greenshot/)
- Microsoft Snipping Tool (Included with Windows Vista+)
 
 Note one can also activate Print Screen screendump for DirectX games by setting this registry key:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\DirectDraw\]  
>  EnablePrintScreen = 1

   
 Note the native Windows message box has the ability to copy the message text into the clipboard, by pressing the CTRL+C. This is useful in case one need to Google the error message, or sent it to the application support team, as it will avoid typos.  
  
 Note in Win9x/WinNT then MsPaint can only save image as uncompressed BMP format. When saving a screen dump from 16/32 bit desktop then the file size will be huge. Consider to save the image in 16 or 256 colors by using "Save as..". Alternative it is possible to install a [MS PAINT Codecs](/article/windows-mspaint-filters.html) addon which will allow it to save in GIF and JPEG which can compress the image and make the file size smaller.  
  
 More Info [MS KB173884](http://support.microsoft.com/kb/173884 "How to Capture Screen Shots in Windows Using the Print Screen Key [Q173884]")  