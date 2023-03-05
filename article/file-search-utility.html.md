---
title: 'Create your own file finder utility'
date: '2002-03-01T11:57:14+01:00'
status: publish
permalink: /article/file-search-utility.html
author: Snakefoot
excerpt: 'How to use the FOR keyword in a batch file to search all available partitions for a file mask.'
type: post
id: 71
category:
    - Tips
tag:
    - batch-file
    - file-search
post_format: []
tags:
    - 'file-search,batch-file'
---
Using the FOR command then one can cycle through all drive-letters (A-Z), and for each partition that exists. It will find all the files which matches the mask given as input parameter.  
  
 Create a [batch file](/article/batch-file.html) FILEFIND.BAT with the following contents:

> FOR %%D IN (C D E F G H I J K L M N O P Q R S T U V W X Y Z) DO IF EXIST %%D:\\. DIR %%D:\\%1 /S /P /A /B

 Use the batch file like this to search for files with the extension ".DOC":
 
 > FILEFIND \*.DOC