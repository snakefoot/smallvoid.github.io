---
title: 'Using dynamic javascript links in Favorites/Bookmarks'
date: '2000-01-01T23:42:09+01:00'
status: publish
permalink: /article/ie-javascript-bookmark.html
author: Snakefoot
excerpt: 'Special javascript bookmarks makes it possible to execute scripts on the web page currently being viewed.'
type: post
id: 314
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - favorites
    - java-script
post_format: []
tags:
    - 'java-script,favorites'
---
It is possible to create special javascript links and place them in Favorites/Bookmarks to help out when browsing the Internet. The Javascript gives the ability of making the links dynamic.  
  
 To create a javascript link to see page info about when it was last updated, and whether the page rendering was standard or [quirks mode](http://www.w3.org/International/articles/serving-xhtml/#quirks):

1. Start Internet Explorer and go a web-page like ex. [www.google.com](http://www.google.com/)
2. In the **Favorites**-menu select **Add to Favorites...**
3. Change the name to **Current Page Details** and press **Ok**
4. In the **Favorites**-menu right-click the newly created link **Current Page Details** and select **Properties**
5. Select the **Web Document**-tab and change the URL to the following, and press **Ok** (Ignore the warning):

  > javascript:alert("Last Updated - " + document.lastModified + "\\nRender Mode - " + document.compatMode)  
  >   
  > [Current Page Details](javascript:alert('Last%20Updated:%20%5Ct'%20+%20document.lastModified%20+%20(document.compatMode%20?%20('%5CnRenderMode:%20%5Ct'%20+%20(document.compatMode=='CSS1Compat'%20?%20'Standard'%20:%20document.compatMode))%20:%20'')%20+%20((document.charset%20%7C%7C%20document.characterSet)%20?%20('%5CnEncoding:%20%5Ct'%20+%20(document.charset%20?%20document.charset%20:%20document.characterSet))%20:%20'Unknown')%20+%20(document.fileSize%20?%20('%5CnPage%20Size:%20%5Ct'%20+%20document.fileSize)%20:%20'')%20);) (Right-click and add to favorites to bookmark)
6. Now when selecting **Current Page Details** it will display a message-box with the modification-time of the page currently shown.
 
 Another useful javascript link is google-translation to english of the page currently shown:
 
 > javascript:document.location = "http://translate.google.com/translate?hl=en&amp;u="+document.location.href;  
>   
> [Current Page Translated](javascript:document.location%20=%20%22http://translate.google.com/translate?hl=en&u=%22+document.location.href;) (Right-click and add to favorites to bookmark)

 Credits [ntcanuck.com/tq](http://ntcanuck.com/tq/)