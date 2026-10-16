---
title: 'Create FAT32 partitions with size below 512 MByte'
date: '2000-01-01T12:26:28+01:00'
permalink: /article/fdisk-small-fat32.html
author: Snakefoot
excerpt: 'How to get fdisk to create small FAT32 partitions with special parameter.'
type: post
id: 73
categories:
    - ms-dos_tips
tags:
    - fat32
    - fdisk
    - partition
---
MS DOS 7.1 will not create FAT32 partitions that are less than 512 MByte. But if starting [Fdisk](/article/fdisk.html) with this parameter, then it can be done:

> FDISK /FPRMT

 Related [Pro and Cons for using multiple partitions](/article/multiple-partitions.html)