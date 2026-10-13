---
title: 'Configure number of rows to show in New Tab Page (about:tabs)'
date: '2012-11-14T22:35:54+01:00'
permalink: /article/ie-about-tabs-rows.html
author: Snakefoot
excerpt: 'How to increase the number of icons displayed for "Your most popular sites" (IE9) or "Frequent sites" (IE10) when you open the about:Tabs page (New Tab page)'
type: post
id: 836
categories:
    - web-browser-internet-explorer-ie9
tags:
    - browsing-session
    - tab-session
---
Internet Explorer 9/10 will by default display "about:tabs" when opening a new tab. It gives the following useful commands in the bottom:

- Reopen closed tabs
- Reopen last session
- [InPrivate Browsing](/article/ie-empty-temporary-internet-files.html)
 
 But it also displays the most recently used web sites with nice icon tiles. By default it will only display the 10 most used websites, but it is possible to add an extra row of websites with this DWORD:
 
> \[HKEY\_CURRENT\_USER\\ Software\\ Microsoft\\ Internet Explorer\\ TabbedBrowsing\\ NewTabPage\]  
>  NumRows = 3

 Credits [blogs.msdn.com/b/ieinternals](http://blogs.msdn.com/b/ieinternals/archive/2010/09/28/show-more-rows-of-sites-on-ie9-about-tabs-homepage.aspx)