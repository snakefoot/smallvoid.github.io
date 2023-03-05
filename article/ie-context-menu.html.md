---
title: 'Extend Internet Explorer context-menu'
date: '2005-02-19T00:42:35+01:00'
status: publish
permalink: /article/ie-context-menu.html
author: Snakefoot
excerpt: 'Extending the right click context menu in Internet Explorer with different useful actions.'
type: post
id: 321
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - context-menu
post_format: []
tags:
    - context-menu
---
The right-click popup-menu in Internet Explorer (IE) can be extended to provide even more useful actions than it has already. Extensions are added through the registry:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\MenuExt **\\My Extension**\]  
>  (Default) = "C:\\MyExtension.html"  
>  Contexts = 34

 The **(Default)**-value specifies what command to execute when the extension is activated. The command must be implemented via a HTML-file, and if one don't like having the HTML-file placed in the root of the C-Drive, then one can just move it to another place like C:\\Windows\\Web.  
 The **Contexts**-value specifies in what context the extension should be shown, and is a bit mask consisting of the logical OR of the following values:
- Default = 0x1
- Images = 0x2
- Controls = 0x4
- Tables = 0x8
- Text selection = 0x10
- Anchor/Link = 0x20

##### Add option to see Google Cache's version of link

1. Add these settings to the registry:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\MenuExt **\\Google Cache**\]  
  >  (Default) = "C:\\GoogleCache.html"  
  >  Contexts = 32
2. Create a text-file named **C:\\GoogleCache.html** with the following contents:
  > &lt;SCRIPT LANGUAGE="JavaScript"&gt;  
  >  var aDestination = "http://www.google.com/search?q=cache:"  
  >  var aWindow = window.external.menuArguments;  
  >  var aDocument = aWindow.document;  
  >  var anEvent = aDocument.parentWindow.event;  
  >  var aLink = anEvent.srcElement;  
  >  aWindow.open(aDestination + aLink);  
  >  &lt;/SCRIPT&gt;

##### Add option to submit text-selection to a search-engine/dictionary

1. Add these settings to the registry:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\MenuExt **\\Google Search**\]  
  >  (Default) = "C:\\GoogleSearch.html"  
  >  Contexts = 16
2. Create a text-file named **C:\\GoogleSearch.html** with the following contents:
  > &lt;SCRIPT LANGUAGE="JavaScript"&gt;  
  >  var aDestination = "http://www.google.dk/search?q="  
  >  var aWindow = window.external.menuArguments;  
  >  var aDocument = aWindow.document;  
  >  var aText = aDocument.selection.createRange().text;  
  >  aWindow.open(aDestination + aText);  
  >  &lt;/SCRIPT&gt;

##### Add option to submit a page for translation

1. Add these settings to the registry:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\MenuExt **\\Google Translate**\]  
  >  (Default) = "C:\\GoogleTranslate.html"  
  >  Contexts = 1
2. Create a text-file named **C:\\GoogleTranslate.html** with the following contents:
  > &lt;SCRIPT LANGUAGE="JavaScript"&gt;  
  >  var aDestination = "http://translate.google.com/translate?hl=en&amp;u="  
  >  var aWindow = window.external.menuArguments;  
  >  aWindow.open(aDestination + external.menuArguments.document.URL);  
  >  &lt;/SCRIPT&gt;
 
 More info [MS KB177241](http://support.microsoft.com/kb/177241 "How To Adding to the Standard Context Menus of the WebBrowser Control [Q177241]")  
 More info [MSDN: About the Browser](http://msdn.microsoft.com/workshop/browser/overview/overview.asp)  
 More info [MSDN: Browser Extensions](http://msdn.microsoft.com/workshop/browser/ext/overview/overview.asp)  
 More info [MSDN: menuArguments Property](http://msdn.microsoft.com/workshop/author/dhtml/reference/properties/menuarguments.asp)  
  
 Credits Laurent Girod