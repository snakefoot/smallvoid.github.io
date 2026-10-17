---
title: 'Configure autocomplete for Internet Explorer'
date: '2003-08-10T00:11:06+02:00'
permalink: /article/ie-autosuggest.html
author: Snakefoot
excerpt: 'Configure the behavior of auto completion in Internet Explorer.'
type: post
id: 317
categories:
    - web-browser_internet-explorer-ie4
    - web-browser_internet-explorer-ie5
    - web-browser_internet-explorer-ie6
tags:
    - autocomplete
    - autosuggest
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
  >  More info <a href="https://www.bing.com/search?q=KB%20157729%20Q157729" rel="nofollow" title="How to Clear the History Entries in Internet Explorer [Q157729]">MS KB157729</a>
 
 One can configure for how long it should remember a typed url:
1. Open **Control Panel**
2. Double click **Internet Options**
3. Select **General** tab
4. Change **Days to Keep Pages in History**
5. Press **Ok**-button
6. It should be reflected with this registry key:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Internet Settings \\Url History\]  
  >  Days To keep = 15
 
 More info <a href="https://www.bing.com/search?q=KB%20217148%20Q217148" rel="nofollow" title="How to use the AutoComplete feature in Internet Explorer 5 and 6 [Q217148]">MS KB217148</a>  
 More info <a href="https://www.bing.com/search?q=KB%20221925%20Q221925" rel="nofollow" title="'Days to Keep Pages in History' Set to 0 Displays Web Sites [Q221925]">MS KB221925</a>  
 More info <a href="https://www.bing.com/search?q=KB%20237553%20Q237553" rel="nofollow" title="Disabling or Enabling the AutoComplete or Inline AutoComplete Feature [Q237553]">MS KB237553</a>  
 More info <a href="https://www.bing.com/search?q=KB%20885180%20Q885180" rel="nofollow" title="The AutoComplete feature does not work after you enable it in Internet Explorer on a computer that is running Windows XP Home Edition [Q885180]">MS KB885180</a>  