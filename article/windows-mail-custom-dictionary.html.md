---
title: 'Remove misspelled word from the custom dictionary'
date: '2007-07-02T07:44:12+02:00'
status: publish
permalink: /article/windows-mail-custom-dictionary.html
author: Snakefoot
excerpt: 'How to remove a word from the custom dictionary incase it has been spelled wrong.'
type: post
id: 644
category:
    - 'Windows Mail (Vista)'
tag:
    - dictionary
    - spell-checking
    - windows-mail
post_format: []
tags:
    - 'windows-mail,spell-checking,dictionary'
---
Windows Mail can perform spellchecking, and it is possible to add new words to the dictionary used. If having added a misspelled word to the custom dictionary, then it can be removed like this:

1. Open the following file in notepad:
   > %USERPROFILE%\\Appdata\\Local\\Microsoft\\Windows Mail\\UserDictionary.lex
2. Find the word that have been spelled wrong and remove it. Make sure not to leave any blank lines.
3. Save and close notepad.
 
 The spell checker should now recognize the word as being misspelled again.  
  
 Credits [Winhelponline.com](http://www.winhelponline.com/)