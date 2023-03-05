---
title: 'Creating file shares that are hidden'
date: '2001-01-01T12:50:57+01:00'
status: publish
permalink: /article/hidden-file-shares.html
author: Snakefoot
excerpt: 'Hiding a file-share by changing the name.'
type: post
id: 143
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - microsoft-network
    - network-share
post_format: []
tags:
    - 'network-share,microsoft-network'
---
It is possible to create shares which aren't visible to people browsing the network. To make a hidden share, just add a $ in the end of name for the share:

> \\\\machine\\\\hidden\_share$

 When accessing the shared resource then remember that $ is part of the share name.
- Hidden shares is merely a cosmetic feature, which allows one to remove irrelevant shares that the average user shouldn't have access to. Ex. shares needed only by a certain application.
- Hidden shares should NOT be used for protecting shares from unauthorized access, instead one should use normal access control with password.
 
 Note that it is only Windows-Clients that abide to the rule of not showing "hidden" shares. Linux machines will see the "hidden" shares like any other shares. There also exist applications for Windows which allows to see "hidden" shares on remote machines.