---
title: 'Microsoft .NET Framework NGEN'
date: '2007-07-17T02:14:23+02:00'
status: publish
permalink: /article/winnt-services-clr-optimization.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Microsoft .NET Framework NGEN service.'
type: post
id: 679
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Native Image Generator (NGEN) improves the speed of .NET applications, by caching the result of the Just-in-Time (JIT) compiler so it only has to be performed once.  
  
 The .NET Runtime Optimization Service is only activated when the native image of an .NET application has become invalidated, usually because the application itself or its dependencies has been updated.  
  
 More Info [MSDN Magazine April 2005 - NGEN](http://msdn.microsoft.com/msdnmag/issues/05/04/NGen/default.aspx)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- mscorsvw.exe (clr\_optimization)

##### Supports:

- none

##### Depends:

- none