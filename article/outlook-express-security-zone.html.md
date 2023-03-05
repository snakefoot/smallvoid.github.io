---
title: 'Configure Outlook Express to use a tougher security policy'
date: '2001-09-25T22:35:13+02:00'
status: publish
permalink: /article/outlook-express-security-zone.html
author: Snakefoot
excerpt: 'Changing Outlook Express to open emails in the Restricted Security zone to improve security.'
type: post
id: 284
category:
    - 'Outlook Express'
tag:
    - security-zone
post_format: []
tags:
    - security-zone
---
By standard Outlook Express(OE) allows for ActiveX and Javascripts which opens you for Worm attacks and similar.  
  
 You can configure your Outlook Express to disable such behavior, by setting the security setting to the profile called Restricted Sites (Which by default has ActiveX and more disabled). Even though Microsoft states that it will get less functional then the extra security is better.  
  
 To change to a higher security level in OE, go to menu "Tools" and select "Options" then select the fan "Security" and set the Security Zone to "Restricted Sites"  
  
 To make sure that the security zone "Restricted Sites" is properly configured, go to the Control Panel and select "Internet Options" and select the fan "Security" there you can [configure the security zone](/article/ie-restrict-untrusted.html) "Restricted Sites".  
  
 More Info [MS KB192846](http://support.microsoft.com/kb/192846 "OLEXP: How to Disable Active Scripting in Outlook Express [Q192846]")