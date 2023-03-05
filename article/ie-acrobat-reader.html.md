---
title: 'Faster Acrobat Reader startup with optional plugins'
date: '2004-11-26T00:24:57+01:00'
status: publish
permalink: /article/ie-acrobat-reader.html
author: Snakefoot
excerpt: 'Acrobat Reader can be quite slow to open PDF files in Internet Explorer.'
type: post
id: 319
category:
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - acrobat-reader
    - ie-plugin
    - pdf
post_format: []
tags:
    - 'acrobat-reader,plugins'
---
[Acrobat Reader](http://www.adobe.com/support/downloads/) have become necessary when wanting to read articles on the Internet. Acrobat Reader ver. 5 and 6 can be slow to startup because it has to load several plugins, but it is possible to make these plugins optional and only load the plugins when the document requires them. The slow startup has been fixed with Acrobat Reader ver. 7, but sadly enough that version cannot be used with Win9x.  
  
 Move all plugin files/folders from this location (Also works for ver. 5.0):
 
 > C:\\Program Files\\Adobe\\Acrobat 6.0\\Reader\\Plug\_ins

 To this location:
 
 > C:\\Program Files\\Adobe\\Acrobat 6.0\\Reader\\Optional

 It might be a good idea not to make these plugins optional:
- **EWH32.api** (To view PDF files in the web browser)
- **Search.api** (To enable search functionality)
- **EScript.api** (To enable navigation links in document)
- **Weblink.api** (To enable navigation links in document)
- **printme.api** (To enable print functionality)
 
 Note it is possible to see the nature of the installed plugins, by starting Acrobat Reader and in the **Help**-menu select **About Acrobat Reader Plug-ins**. Then decide from those details whether a plugin should be optional or not.  
  
 Note if making ebook.api optional, then the "My eBooks"-folder in the "My Documents" folder will not be created when starting Acrobat Reader.  
  
 Note if scared of moving files around, then one can also get the same effect, by holding down the SHIFT-key when starting Acrobat Reader.