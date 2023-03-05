---
title: 'Configure autocomplete for Internet Explorer'
date: '2003-08-10T00:11:06+02:00'
status: publish
permalink: /article/ie-autosuggest.html
author: Snakefoot
excerpt: 'Configure the behavior of auto completion in Internet Explorer.'
type: post
id: 317
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - autocomplete
    - autosuggest
post_format: []
tags:
    - 'autocomplete,autosuggest'
---
When typing in an internet url in Internet Explorer, then it can provide listing of url's for Web addresses that matches the beginning letters.  
  
 One can configure whether it should show the drop down list of matching urls:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\AutoComplete\]  
>  AutoSuggest = "No" / "Yes"

 One can configure whether to take the closest match and put it in the address bar while typing:
1. Open **Control Panel**
2. Double click **Internet Options**
3. Select **Advanced** tab
4. Tick/Untick **Use inline AutoComplete**
5. It should be reflected with this registry key:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\AutoComplete\]  
  >  Append Completion = "No" / "Yes"
 
 One can clear the auto complete dropdown list (Index.dat file in the History folder):
1. Open **Control Panel**
2. Double click **Internet Options**
3. Select **General** tab
4. Press **Clear History**-button
5. Select **Content** tab
6. Press **Auto Complete**-button
7. Make sure that **Web Addresses** is checked and press **Clear Forms**
8. Press **Ok**-button
9. Also check that no entries is listed at the following registry key:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\TypedURLs\]  
  >   
  >  More info [MS KB157729](http://support.microsoft.com/kb/157729 "How to Clear the History Entries in Internet Explorer [Q157729]")
 
 One can configure for how long it should remember a typed url:
1. Open **Control Panel**
2. Double click **Internet Options**
3. Select **General** tab
4. Change **Days to Keep Pages in History**
5. Press **Ok**-button
6. It should be reflected with this registry key:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Internet Settings \\Url History\]  
  >  Days To keep = 15
 
 More info [MS KB217148](http://support.microsoft.com/kb/217148 "How to use the AutoComplete feature in Internet Explorer 5 and 6 [Q217148]")  
 More info [MS KB221925](http://support.microsoft.com/kb/221925 ""Days to Keep Pages in History" Set to 0 Displays Web Sites [Q221925]")  
 More info [MS KB237553](http://support.microsoft.com/kb/237553 "Disabling or Enabling the AutoComplete or Inline AutoComplete Feature [Q237553]")  
 More info [MS KB885180](http://support.microsoft.com/kb/885180 "The AutoComplete feature does not work after you enable it in Internet Explorer on a computer that is running Windows XP Home Edition [Q885180]")  