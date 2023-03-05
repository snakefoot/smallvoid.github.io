---
title: 'Configure the branding of Internet Explorer'
date: '2000-01-01T22:30:39+01:00'
status: publish
permalink: /article/ie-branding.html
author: Snakefoot
excerpt: 'Internet Explorer can be modified to display company name or company pictures.'
type: post
id: 311
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
    - 'Internet Explorer (IE7)'
tag:
    - branding
post_format: []
tags:
    - branding
---
3rd party vendors like to brand the IE which is delivered with their software/hardware.  
 You can configure this branding yourself:

- To Change the IE4, IE5, IE6 title which default is "Microsoft Internet Explorer", go to this registry entry:
  > \[HKEY\_CURRENT\_USER /Software /Microsoft /Internet Explorer /Main\]  
  >  Window Title="Your Title Text"
- To change the IE4 toolbar bitmap, go to this registry entry:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Toolbar\]  
  >  BackBitmap="c:\\pics\\pamela.bmp"
- To change the IE5, IE6 toolbar bitmap, go to this registry entry:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Toolbar\]  
  >  BackBitmapIE5="c:\\pics\\pamela.bmp"
- To change the top right corner animation:
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Internet Explorer \\Main\]  
  >  BigBitmap="c:\\pics\\big\_image\_start.bmp"  
  >  SmallBitmap="c:\\pics\\small\_image\_start.bmp"  
  >   
  >  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Toolbar\]  
  >  BrandBitmap="c:\\pics\\big\_image\_ani.bmp"  
  >  SmBrandBitmap="c:\\pics\\small\_image\_ani.bmp"
  
  
  - big\_image\_start.bmp : 38 x 38 pixel image
  - small\_image\_start.bmp : 22 x 22 pixel image
  - big\_image\_ani.bmp : 38 x 1178 pixel image (31 vertical placed images of 38 x 38 pixel)
  - small\_image\_ani.bmp : 22 x 682 pixel image (31 vertical placed images of 22 x 22 pixel)
   
   More Info [MS KB176713](http://support.microsoft.com/kb/176713 "How to Restore the Animated Internet Explorer Logo [Q176713]")
- To change the organization name of Internet Explorer 7:
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\IEAK7\]  
  >  Organization Name = "Your Organization Name"
 
 It is possible to clear these brandings completely, by running this command :  
> Rundll32 Iedkcs32.dll,Clear  
>   
>  More Info [MS Technet](http://www.microsoft.com/technet/prodtechnol/ie/reskit/6/part5/c20ie6rk.mspx "Chapter 20 - Running the Microsoft Internet Explorer Customization Wizard")

 Note Internet Explorer 7 (IE7) includes a new feature called "Reset Internet Explorer Settings" (RIES). To activate RIES open Control Panel -&gt; Internet Options... -&gt; Advanced-tab and press Reset. As the name reveals it changes most IE settings back to default. After RIES is done then it re-applies the branding rules specified here, unless the file have been deleted:
 > %ProgramFiles%\\Internet Explorer\\CUSTOM\\install.ins

 IE7 RIES should only be used as the last resort as it clears out a lot of settings. More Info [MS KB923737](http://support.microsoft.com/kb/923737 "How to use Reset Internet Explorer Settings (RIES)"): - Home pages
- Search scopes
- Browsing history
- Form data
- Passwords
- Appearance settings
- Toolbars
 
 Credits [PC Forrest](http://www.forrestandassociates.co.uk/pcforrest/)