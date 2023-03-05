---
title: 'Customize folders using the Active Desktop Web View'
date: '2003-09-06T00:11:43+02:00'
status: publish
permalink: /article/windows-web-content.html
author: Snakefoot
excerpt: 'Active Desktop enables customization of folders like they were web pages.'
type: post
id: 305
category:
    - Desktop
    - Desktop
    - Desktop
tag:
    - active-desktop
    - custom-folders
    - visual-style
post_format: []
tags:
    - 'custom-folders,active-desktop,visual-style'
---
Active Desktop has a feature called Web Content or Web View that allows one to customize the look of file folders. One can configure a file folder to have a preview pane, which shows certain file details when a file in the folder is selected (If a picture-file it can show the image).  
  
 Customize a single file folder:

1. Browse to the folder using explorer
2. In the menu select **View** and **Customize Folder**
3. In the Wizard select **Choose or edit an Hyper Text Markup Language (HTML) template for this folder**
4. Press **Next** and choose the **Standard**-template and tick **I want to edit this template**
5. Press **Next** and open the default-template in your default HTML editor where you can change what ever you like
6. In the folder a hidden file **desktop.ini** is created, which refers to the modified template
 
 Customize a single file folder to stop the Media Player preview of movie-files:
1. Use the above steps to open the default-template in your default HTML editor
2. Search for the string **function IsMovieFile**
  > function IsMovieFile(ext) {  
  >  var types = ",asf,avi,m1v,mov,mp2,mpa,mpe,mpeg,mpg,mpv2,qt,asx,";  
  >  var temp = ","+ext+",";  
  >  return types.indexOf(temp) &gt; -1;  
  >  }
3. Change the function so it will not recognize any file as a movie file:
  > function IsMovieFile(ext) {  
  >  **return false;**  
  >  var types = ",asf,avi,m1v,mov,mp2,mpa,mpe,mpeg,mpg,mpv2,qt,asx,";  
  >  var temp = ","+ext+",";  
  >  return types.indexOf(temp) &gt; -1;  
  >  }
4. Save the changes to the template file and now media preview of movie files should be turned off for that folder.
 
 Making the customization of one folder, the default for all folders:
1. Browse to the customized folder using explorer
2. In the folder open the hidden file **desktop.ini** using notepad
3. Find the text-line **PersistMoniker** to see the folder containing the customized htt-file (The folder is relative to the C-Drive)
4. Browse to the folder %Windir%\\Web and make a backup of the default template **folder.htt**
5. Browse to the folder containing the customized htt-file and copy it to %windir%\\Web so it overwrites **folder.htt**
 
 Related [Remove warning about modifying contents in the Windows-folder](/article/windows-folder-warning.html)  
  
 More Info [MS MSDN: Extending Explorer Views by Customizing Hypertext Template Files](http://msdn.microsoft.com/en-us/magazine/cc302292.aspx "MSDN Magazine June 2000 - More Windows 2000 UI Goodies: Extending Explorer Views by Customizing Hypertext Template Files")  
 More Info [MS MSDN: Customizing a Folder's Web View](http://msdn.microsoft.com/en-us/library/bb776835.aspx)  
 More Info [MS MSDN: Customizing Folder icon with Desktop.ini](http://msdn.microsoft.com/en-us/library/cc144102.aspx)  