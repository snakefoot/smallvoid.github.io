---
title: 'Configure Windows Search to index file contents'
date: '2008-12-25T20:41:11+01:00'
status: publish
permalink: /article/winnt-search-file-content.html
author: Snakefoot
excerpt: 'Configure Windows Search index filters to perform indexing of document and spreadsheets using IFilters.'
type: post
id: 785
category:
    - Tips
    - Tips
tag:
    - file-search
    - indexing-service
post_format: []
tags:
    - 'file-search,indexing-service'
---
Microsoft Windows Search will by default index all file-names and their properties, but it also has support for searching the contents of files.  
  
 By default it can search simple document formats like plain text files and html files, but it is possible to install filters so more advanced document formats also can be indexed. Making it possible to find the right document by just providing the search-words that the document contains.

- [Download Microsoft Filter Pack](http://www.microsoft.com/downloads/details.aspx?FamilyId=60C92A37-719C-4077-B5C6-CAC34F4227CC) - Will enable indexing of Microsoft Office documents like Word, Excel, Access, PowerPoint, etc. (.docx, .docm, .pptx, .pptm, .xlsx, .xlsm, .xlsb, .zip, .one, .vdx, .vsd, .vss, .vst, .vdx, .vsx, and .vtx.)
- [Download Adobe PDF iFilter](http://www.adobe.com/support/downloads/detail.jsp?ftpID=2611) - Will enable indexing of Adobe PDF documents. The iFilter is bundled together with Adobe Reader from version 7.05.
- [Download Foxit PDF iFilter](http://www.foxitsoftware.com/pdf/ifilter/) - If their filter is just as good as their PDF reader, then this should blow Adobe off the board.
 
 More Info [ifilter.org](http://www.ifilter.org/)  
  
 Credits [LifeHacker.com](http://lifehacker.com/5063906/filter-pack-adds-office-doc-contents-to-windows-search)