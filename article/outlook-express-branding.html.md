---
title: 'Configure Outlook Express branding'
date: '2002-02-02T17:53:25+01:00'
status: publish
permalink: /article/outlook-express-branding.html
author: Snakefoot
excerpt: 'How to put the company name in the title of the Outlook Express application.'
type: post
id: 328
category:
    - 'Outlook Express'
tag:
    - branding
post_format: []
tags:
    - branding
---
3rd party vendors like to brand the OE which is delivered with their software/hardware.  
  
 You can configure this branding yourself:

- To change the OE4 title, go to this registry entry:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Outlook Express\]  
  >  Window Title="Your Title Text"
- To change the OE5, OE6 title, go to this registry entry: (Notice no space in WindowTitle)
  > \[HKEY\_CURRENT\_USER \\Identities \\{GUID} \\Software \\Microsoft \\Outlook Express \\5.0\]  
  >  WindowTitle="Your Title Text"
 
 Credits [PC Forrest](http://www.forrestandassociates.co.uk/pcforrest/)