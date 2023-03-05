---
title: 'Configure the picture used as background wallpaper'
date: '2002-03-30T23:07:09+01:00'
status: publish
permalink: /article/windows-wallpaper.html
author: Snakefoot
excerpt: 'Configuring how the wallpaper should be displayed using registry settings.'
type: post
id: 294
category:
    - Desktop
    - Desktop
    - Desktop
tag:
    - background-picture
    - wallpaper
post_format: []
tags:
    - 'wallpaper,background-picture'
---
For some unknown reason one is not able to do stretch without installing an addon. Now you can do it without an addon.  
  
To specify wallpaper to use, has to be a bmp with a 8.3 path format (REG\_SZ):
 > \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
 >  Wallpaper = "c:\\image\\pamela.bmp"

To specify tiling of the wallpaper (REG\_SZ):
 > \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
 >  TileWallpaper = "1" (0 for non-tile)

To specify stretching of the wallpaper (REG\_SZ):
> \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
>  WallpaperStyle = "2" (0 for non-Stretch)

To specify start location of centered (Non-Tiled and Non-Stretched) wallpaper (REG\_SZ):
> \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
>  WallPaperOriginX = "1" (Pixels)  
>  WallPaperOriginX = "2" (Pixels)

 More Info [MS KB135599](http://support.microsoft.com/kb/135599 "How To Reposition a Centered Wallpaper Bitmap on The Desktop [Q135599]")  
 More Info [MS KB257665](http://support.microsoft.com/kb/257665 "Cannot Disable "Stretch Wallpaper" Feature [Q257665]")  