---
title: DIR2XML
date: '2006-01-01T03:21:32+01:00'
status: publish
permalink: /article/dir2xml.html
author: Snakefoot
excerpt: 'Directory listing in XML using VBScript.'
type: post
id: 643
category:
    - Uncategorized
tag:
    - dir2xml
    - directory
    - vbscript
post_format: []
tags:
    - 'dir2xml,directory,vbscript'
---
##### Introduction

 DIR2XML is a VBScript that works like the dir command, but outputs the result in a [XML](http://www.w3schools.com/xml/ "XML Tutorial") file. The XML file can be converted to any other format using XSLT, which gives different possibilities by creating the right [XSL](http://www.w3schools.com/xsl/ "XSLT Tutorial") file:
- Scan a directory and output a playlist for all MP3 files (M3U).
- Scan a directory and output a text report (CSV) that lists all EXE/DLL files with version info.
- Scan a directory and output a HTML Web Page containing the file names and can be published on the Internet ([Example](/tweak/winnt/files/winxpsp2st.htm)).

##### How to use:

1. Download the [DIR2XML.ZIP](/tweak/windows/dir2xml/dir2xml.zip) and extract it to a directory
2. Go to the directory and double-click **DIR2XML.VBS**, and a directory-dialog will popup
3. Use the directory-dialog to specify the directory to scan (Careful directories with many files will take a long time to scan)
4. Press Ok and it will scan the directory, when having scanned the directory it will say "DIR2XML Completed"
5. The directory with **DIR2XML.VBS** will now also contain two new files **DIR2XML.XML** and **DIR2XML.HTML**, which can be viewed by Internet Explorer

##### Version history:

- Version 1.0 (Initial) 
  - Outputs file-name, -path, -type, -extension, -version, -size, -modified date
  - Outputs the file details sorted by directory and then filename
  - Support command line arguments for specifying xml-, xsl- and output-file
  - Includes a simple XSL for converting the XML into XHTML