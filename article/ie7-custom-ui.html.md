---
title: 'Customize the looks of Internet Explorer 7'
date: '2007-01-27T18:02:00+01:00'
status: publish
permalink: /article/ie7-custom-ui.html
author: Snakefoot
excerpt: 'Registry settings for changing the user interface of Internet Explorer 7.'
type: post
id: 196
category:
    - 'Internet Explorer (IE7)'
tag:
    - command-bar
    - menu-bar
    - search-bar
post_format: []
tags:
    - 'menu-bar,command-bar,search-bar'
---
Internet Explorer 7 includes many changes to the user interface, but it is possible to change certain things back.

##### Display the menu-bar at the top:

 Can be shown temporarily by holding down the ALT key.
1. Click the Tools-menu (Right of the Tab-bar) and check "Menu bar"
2. Place the menu-bar above the address-bar with this registry key:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Toolbar \\WebBrowser\]  
  >  ITBar7Position = 1  
  >   
  >  More Info [MS KB930645](http://support.microsoft.com/kb/930645 "How to move the Standard toolbar to a location that is above the Address bar in Internet Explorer 7")

##### Remove the search-bar:

> \[HKEY\_CURRENT\_USER \\Software \\Policies \\Microsoft \\Internet Explorer \\InfoDelivery \\Restrictions\]  
>  NoSearchBox = 1

##### Remove the command-bar shortcuts:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\CommandBar\]  
>  Enabled = 0

##### Remove the command-bar entirely:

 Will disable Favorites, Feeds and History. > \[HKEY\_CURRENT\_USER \\Software \\Policies \\Microsoft \\Internet Explorer \\Toolbars \\Restrictions\]  
>  NoCommandBar = 1

 Credits [Winhelponline.com](http://www.winhelponline.com/)