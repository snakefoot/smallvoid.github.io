---
title: 'Using function keys to enhance the command prompt'
date: '2002-01-01T12:58:15+01:00'
status: publish
permalink: /article/winnt-command-prompt-shortcuts.html
author: Snakefoot
excerpt: 'The command prompt allows one to use shortcut keys for easier navigation.'
type: post
id: 459
category:
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
tag:
    - keyboard
    - shortcut-keys
post_format: []
tags:
    - 'shortcut-keys,keyboard'
---
When having started a command prompt (cmd.exe) console window, then one can use the following function keys:

- **F1 :** Repeats the letters of the last command line, one by one
- **F2 :** Displays a dialog asking user to "enter the char to copy up to" of the last command line
- **F3 :** Repeats the last command line (Similar to DOSKEY)
- **F4 :** Displays a dialog asking user to "enter the char to delete up to" of the last command line
- **F5 :** Goes back one command line
- **F6 :** Enters the traditional CTRL+Z (^z) (End-Of-File)
- **F7 :** Displays a menu with the command line history (Similar to DOSKEY) 
  - ALT + F7 will clear the command line history
- **F8 :** Cycles back through previous command lines (beginning with most recent). If having typed the first few letters for the wanted command, then it will only cycle through the previous commands matching that prefix when pressing F8.
- **F9 :** Displays a dialog asking user to enter a command number, where 0 is for first command line entered
 
 Note when pressing the arrow-keys up and down it will go through the previous executed command lines.  
  
 Note the function keys will only work when starting command prompt with Cmd.exe, they will not work if running the MS-DOS emulator Command.com.  
  
 Note that the default buffer can only store 50 command lines, if using more then the first will be deleted. One can increase this limit by changing "Buffer Size" in "Command History" (ALT+Spacebar p).  
  
 Note one can use the mouse for copy and paste:
  - **Copy** - Hold down the left mouse button and drag the mouse in the command prompt window to select the text, and right click to copy the marked text to clipboard. 
  - "Quick Edit Mode" (Enabled by default) is required for selecting text by left clicking, else one have to change to mark-mode (ALT+Spacebar ek) first.
  - If running an application in the console, then it will be paused if selecting text in the console. Disabling "QuickEdit Mode" will keep one from accidently pausing a console application using the left mouse button.
  - If running an application in the console, then scroll-mode (ALT+Spacebar el) is useful to scroll the output instead of selecting text to pause the scrolling.
- **Paste**
  - Right click to paste the contents of the clip board to the command prompt. If having activated "QuickEdit mode" then it will paste right away, else it will display a context menu with the option to do a paste.
 
 Note to close the command prompt, then either type the command "exit", or hold down the ALT-key and press the spacebar (Opens the system menu) and then press the C-key.  
  
 Related [Configure shortcut keys for file and directory completion](/article/winnt-file-directory-completion.html)  
 Related [Using keyboard shortcuts/hotkeys to quickly access programs](/article/windows-keyboard-shortcuts.html)  
 Related [Disable the windows key on the keyboard](/article/winnt-scancode-map.html)  
  
 Credits [ntcanuck.com/tq](http://ntcanuck.com/tq)