---
title: 'Adding FTP server / WebDAV folder as a network place'
date: '2007-09-01T09:20:15+02:00'
status: publish
permalink: /article/winnt-web-network-place.html
author: Snakefoot
excerpt: 'Use Windows Explorer to browse a remote internet server by adding it as a network place.'
type: post
id: 739
category:
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - ftp
    - ftp-client
    - network-places
    - webdav
post_format: []
tags:
    - 'webdav,ftp,ftp-client,network-places'
---
Windows Explorer has the same FTP and HTTP capabilities as [Internet Explorer](/article/ie-ftp-client.html), so it is possible to add FTP and HTTP servers as Network Places. This allows one to access them like bookmarked Web Folders where one can easily upload and download files using the Windows Explorer.

##### To add a Web Folder as a network place in Win98/WinNT4

 If using Win98 or WinNT4 and doesn't see a "Web Folders" icon in "My Computer", then one need to install the "Web Folders component" of Internet Explorer 5.x first. More Info [MS KB298637](http://support.microsoft.com/kb/298637 "No option to install Web Folders when you install Internet Explorer 6").
1. Open **My Computer** and double click **Web Folders** and double-click **Add Web Folder**.
2. Enter the address of the remote server and click **Next**. 
  - If using WebDAV over SSL then use https instead of http
3. Type the username and password to use for logging in and click **OK**. 
  - For anonymous access change the username to anonymous and blank password
4. Give the new network place a name (it will become the name shown in the Web Folders), and click **Finish**.

##### To add a Web Folder as a network place in Win2k/WinMe

1. Open **My Computer** and in the menu **Tools** select **Map Network Drive...**
2. Click the blue link to Create a shortcut to a **Web folder or FTP site**.
3. Enter the address of the remote server (See the examples of how the paths should be entered) and click **Next**
  - If using WebDAV over SSL then use https instead of http
4. If anonymous access check **Log on anonymously** else uncheck it and enter the account username and click **Next**
5. Give the new network place a name (it will become the name shown in the My Network Places), and click **Finish**.

##### To add a Web Folder as a network place in WinXP/Win2k3

 Win2k3 doesn't have the Web Extender Client component by default, and has to use the installer package Webfldrs.msi from a Windows 2000 or XP installation. More Info [MS KB888123](http://support.microsoft.com/kb/888123 "You cannot connect to a Web folder from a Windows Server 2003 or Windows XP x64 machine")1. Open the **Control Panel** and click **Network and Internet Connections**.
2. Under **See Also**, click **My Network Places**.
3. Click **Add a network place**. The Add Network Place Wizard starts. Click **Next** to continue.
4. Click **Choose another network location**, and then click **Next**.
5. Enter the address of the remote server (See the examples of how the paths should be entered) and click **Next**
  - If using WebDAV over SSL then use https instead of http
6. Click **Next** and give the network place a name and click **Next** again and then **Finish**. More Info [MS KB308416](http://support.microsoft.com/kb/308416 "HOW TO: Create a Shortcut to a Network Location in Windows XP [Q308416]")

##### To add a Web Folder as a network place in Vista

1. Click on the **Start** menu and choose **Computer**.
2. Click the **Map network drive** button in the toolbar.
3. Click the blue link **Connect to a Web site that you can use to store your documents and pictures**.
4. The Add Network Location starts. Click **Next** to continue.
5. Select the **Choose a custom network location** option and click **Next**.
6. Enter the location of the FTP site (See the examples of how the paths should be entered) and click **Next**. 
  - If using WebDAV over SSL then use https instead of http
7. If anonymous login then check check **Log on anonymously**, else uncheck the box and enter the username of the FTP account and click **Next**.
8. Give the new network place a name (it will become the name shown in the Computer window), and click **Finish**.

##### Microsoft Hotfixes for WebDAV on Windows

 Microsoft have released an update to the Web Folders component, which fixes several issues with WebDAV folders. More Info [MS KB907306](http://www.microsoft.com/downloads/details.aspx?FamilyId=17C36612-632E-4C04-9382-987622ED1D64).
 - The latest version of the Web Folders update (2.0) doesn't support Windows 98, Me or 2000. Instead one should use version 11.0.6715.15 [Download Webfldrs-KB892211-ENU.exe](http://smallvoid.orgfree.com/?file=Webfldrs-KB892211-ENU.exe.zip).
 - Windows Vista SP1 (and older) has a known bug where it cannot access sub-folder unless it has read-access to the parent folders. More Info [MS KB942392](http://support.microsoft.com/kb/942392 "On a Windows Vista-based computer, you cannot access certain directories on a WebDAV server")
 
 More Info [MS KB287402](http://support.microsoft.com/kb/287402 "Troubleshooting Web Folders") (Troubleshooting Web Folders)  
 More Info [Lists WebDAV clients in MS Office (and their bugs)](http://greenbytes.de/tech/webdav/webfolder-client-list.html "Web Folder Client (MSDAIPP.DLL) Versions and Issues List")  
 More Info [Lists WebDAV clients in Windows (and their bugs)](http://greenbytes.de/tech/webdav/webdav-redirector-list.html "WebDAV Mini-Redirector (MRXDAV.SYS) Versions and Issues List")  
  
 Related [Mapping WebDAV folder as a network drive letter](/article/winnt-webdav-network-drive.html)  
 Related [Mapping FTP server as network drive letter](/article/ftp-map-network-drive.html)  