---
title: 'Microsoft Baseline Security Analyzer'
date: '2003-07-27T17:42:38+02:00'
status: publish
permalink: /article/winnt-security-analyzer.html
author: Snakefoot
excerpt: 'Utility for analyzing the computer configuration and alerts if any security issues are detected.'
type: post
id: 512
category:
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag: []
post_format: []
---
The [Microsoft Baseline Security Analyzer](http://www.microsoft.com/technet/security/tools/mbsahome.mspx) (MBSA) can scan Microsoft Windows NT for security issues and missing security patches.  
  
 If you don't have access to Microsoft when checking for missing security patches download [Mssecure.cab](http://go.microsoft.com/fwlink/?LinkId=18922) and place in the folder where MBSA was installed. Even if the mssecure.cab is installed the MBSA will still try to contact Microsoft, but the scan will still work if the contact should fail because of a firewall.  
  
 Note if using antivirus that scans archives, then one might want to exclude Mssecure.cab, as it might introduce slow performance.  
  
 Note in Win2k if not having installed "Client for Microsoft Networks" for the Network Adapter (Don't need to be bound), then the MBSA will report at critical problem about "Computer not found."  
  
 More Info [MBSA Q&amp;A](http://www.microsoft.com/technet/security/tools/mbsaqa.mspx)