---
title: 'Configure header and footer when printing web-pages'
date: '2005-12-20T01:04:46+01:00'
status: publish
permalink: /article/ie-print-webpage.html
author: Snakefoot
excerpt: 'Internet Explorer has the ability to print web-pages and can put a custom header and footer on the printed page.'
type: post
id: 323
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - footer
    - header
    - printer
post_format: []
tags:
    - 'printer,header,footer'
---
When printing web-pages from Internet Explorer (Ex. an online book), then Internet Explorer (IE) will insert its own header and footer on each page which doesn't always look good. Open the File-menu and select Page Setup to configure the way it is printed.  
  
 The default header layout is Page-title followed by Page X of X:

> &amp;w&amp;bPage &amp;p of &amp;P

 The default footer layout is Page-URL followed by Current date:

> &amp;u&amp;b&amp;d

 To understand what the different letters means, then use the following chart to see what the different variables mean (or just press F1 when having placed the cursor in the header/footer-field):  
  
<table border="1" width="50%"><tr><th>Option</th><th>Result</th></tr><tr><td>&amp;w</td><td>Windows Title (Page title)</td></tr><tr><td>&amp;u</td><td>Page URL</td></tr><tr><td>&amp;d</td><td>Current date in short format</td></tr><tr><td>&amp;D</td><td>Current date in long format</td></tr><tr><td>&amp;t</td><td>Current time</td></tr><tr><td>&amp;T</td><td>Current time in 24-hour format</td></tr><tr><td>&amp;p</td><td>Current page number</td></tr><tr><td>&amp;P</td><td>Total number of pages</td></tr><tr><td>&amp;&amp;</td><td>A single "&amp;"</td></tr><tr><td>&amp;b</td><td>Text immediately following this character is centered</td></tr><tr><td>&amp;b&amp;b</td><td>The text immediately following the first "&amp;b" is centered, while the text following the second is right-justified.</td></tr></table>

  
 More Info [MS KB306786](http://support.microsoft.com/kb/306786 "How to Print a Web Page in Internet Explorer 5.5 [Q306786]")  
  
 Note when printing HTML mails in Outlook, then it will use the Page Setup settings in Internet Explorer. If the margins are set to small, then it might cut off a part of the page. Setting all four margins to .75 should solve this.  
  
 Note when printing HTML mails in Outlook Express, then it will use the font size currently selected in Internet Explorer. If the text is too small or too large, then it can be adjusted by starting Internet Explorer and in the menu select **View** and change the **Text Size**. More Info [MS KB276435](http://support.microsoft.com/kb/276435 "OLEXP: Large or Small Font Printing Message from Outlook Express [Q276435]")  
  
 Credits [Internet-Explorer-Tutorials.com](http://internet-explorer-tutorials.com/)