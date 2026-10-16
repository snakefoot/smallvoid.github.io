---
title: 'Start Internet Explorer with extensions and addons disabled'
date: '2006-11-02T20:27:44+01:00'
permalink: /article/ie7-disable-extensions.html
author: Snakefoot
excerpt: 'Disabling the browser helper objects can be useful when troubleshooting Internet Explorer.'
type: post
id: 327
categories:
    - web-browser_internet-explorer-ie7
    - web-browser_internet-explorer-ie8
    - web-browser_internet-explorer-ie9
tags:
    - command-line-switches
    - ie-plugin
    - safemode
---
Internet Explorer (IE) 7/8/9/10 allows the use of Browser Helper Objects (BHO's), which can be used to extend Internet Explorer with additional features. BSO's are loaded when IE starts, so if a BHO cannot start, then IE might not be able to load properly.  
  
 It is possible to launch IE without loading installed BHO's, which can be useful for troubleshooting:

> iexplore -extoff

 More Info [IE7 Quick Reference Sheet](http://www.microsoft.com/windows/ie/ie7/about/quickreference.mspx)  
  
 Credits [jsifaq.com](http://jsifaq.com/)