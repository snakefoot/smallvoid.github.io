---
title: 'Reset IE Content Advisor password'
date: '2000-01-01T22:41:05+01:00'
status: publish
permalink: /article/ie-content-advisor.html
author: Snakefoot
excerpt: 'Recover access to the content advisor configuration by resetting the password.'
type: post
id: 312
category:
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - content-advisor
    - parental-control
    - password
    - password-recovery
post_format: []
tags:
    - 'content-advisor,password,password-recovery,parental-control'
---
The Content Advisor allows one to block certain sites from being viewed, mostly in the interest of Parental Control to keep children away from the more obscure sites like [goatse.cx](http://en.wikipedia.org/wiki/Goatse.cx).  
  
 It is possible to password protect the Content Advisor configuration, with the sudden possibility of forgetting the password and one need to reset it when not able to remember it.  
  
 This can be done in the registry, just delete the value **Key** which is found at this registry key.

> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\Ratings\]  
>  Key=?

 After deleting the registry key then go to Control Panel -&gt; Internet Options -&gt; Content-tab -&gt; Settings-button and press the Cancel-button when asked for password. Now the Content Advisor should be disabled.  
  
 Note another way to remove the password is to delete/rename the used Content Advisor Profile (A hidden file usually found in Windows\\System-folder):
 
 > Ratings.pol

 After deleting the file then go to Control Panel -&gt; Internet Options -&gt; Content-tab -&gt; press Ok-button. Now the Content Advisor should be disabled. This also seem to work if unable to disable Content Advisor even if one knows the password.  
  
 More Info [MS KB242037](http://support.microsoft.com/kb/242037 "Error Message: Please Check Your Content Advisor Settings for Missing Information [Q242037]")  
 More Info [MS KB310401](http://support.microsoft.com/kb/310401 "HOW TO: Use the Internet Explorer 6 Content Advisor to Control Access to Web Sites in Internet Explorer")  
 More Info [Browse the Web with Content Advisor](http://www.microsoft.com/windows/ie/ie6/using/howto/security/contentadv/config.mspx)  
 More Info [Description of Content Advisor](http://technet.microsoft.com/en-us/library/dd361897.aspx "Microsoft Internet Explorer 6 Resource Kit - Chapter 5")  
 More Info [Content Advisor in Windows Vista](http://technet.microsoft.com/en-us/library/cc749121.aspx "Using Windows Vista: Controlling Communication with the Internet - Appendix J")  