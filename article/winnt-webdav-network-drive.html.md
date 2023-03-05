---
title: 'Mapping WebDAV folder as a network drive letter'
date: '2007-09-01T09:19:56+02:00'
status: publish
permalink: /article/winnt-webdav-network-drive.html
author: Snakefoot
excerpt: 'Mount a Web Folder as a mapped network drive with help from the Webclient service.'
type: post
id: 738
category:
    - Network
    - Network
    - Network
tag:
    - drive-mount
    - network-drive
    - webdav
post_format: []
tags:
    - 'webdav,network-drive,drive-mount'
---
Web-based Distributed Authoring and Versioning (WebDAV) is an extension to the HTTP protocol, which makes it possible to manage files on a remote Web-Server. WebDAV is preferred when clients has to connect through an insecure network (like the Internet) to reach the remote server, as the remote server can be protected by a firewall and only leaving the HTTP port open and allows SSL instead of using VPN.  
  
 Windows XP includes the [WebClient service](/article/winnt-services-webclient.html) that allows one to mount a Web Folder as a mapped network drive:

> net use x: "http://server.com/folder" /User:UserName Password  
>   
>  Note to make the mapping permanent add the parameter /persistent:yes  
>   
>  Note Windows XP can only connect to port 80 and can only map to a sub folder and not the root directly.

 If wanting to make a secure SSL mapping using the https protocol at port 443:
> net use x: "\\\\server.com@ssl:443\\folder" /User:UserName Password  
>   
>  net use x: "https://server.com/folder" /User:UserName Password  
>   
>  Note Windows XP only supports SSL / https connections when using [My Network Places](/article/winnt-web-network-place.html), but can be tricked into using SSL with net use by creating a forward server using [stunnel](http://www.stunnel.org/). More Info [Simple Groupware WebDAV](http://www.simple-groupware.de/cms/Main/WebDAV).

 Windows Vista can create a network drive without needing to dive into the command line:
1. Click on the **Start** menu and choose **Computer**.
2. Click the **Map network drive** button in the toolbar.
3. Select the drive-letter and enter the WebDAV location in the **Folder** using the http address.
4. Click the blue link "Connect using a **different username**" to specify a different user account and password, than the Windows user account.
5. Click **Finish** to create the new drive letter.
 
 Note there is an update available for Windows XP/Vista for better support of WebDAV folders (Will be part of XP SP3 and Vista SP1). More Info [MS KB907306](http://support.microsoft.com/kb/907306 "Description of the Software Update for Web Folders: May 18, 2007"). - The latest version of the Web Folders update (2.0) doesn't support Windows 98, Me or 2000. Instead one should use version 11.0.6715.15 [Download Webfldrs-KB892211-ENU.exe](http://smallvoid.orgfree.com/?file=Webfldrs-KB892211-ENU.exe.zip).
- Windows Vista SP1 (and older) has a known bug where it cannot access sub-folder unless it has read-access to the parent folders. More Info [MS KB942392](http://support.microsoft.com/kb/942392 "On a Windows Vista-based computer, you cannot access certain directories on a WebDAV server")
 
 Note if using Windows 2000 or earlier, then one must use a 3rd party [utility to map a WebDAV folder as a network drive](/article/ftp-map-network-drive.html).  
  
 Note MS Office (2000+) includes its own WebDAV client which supports file locking and SSL, but will only work when accessing files through the office applications (Excel, Word, etc.). More Info [MS KB838028](http://support.microsoft.com/kb/838028 "How documents are opened from a Web site in Office 2003")  
  
 Note to setup a WebDAV server for the clients to connect to, then one can use [IIS](http://support.microsoft.com/kb/323470 "How to create a secure WebDAV publishing directory [Q323470]") or try one of these freeware servers: - [Apache](http://httpd.apache.org/)
- [LightTPD](http://wlmp.dtech.hu/index.php?lang=en)
 
 More Info [Lists WebDAV clients in MS Office (and their bugs)](http://greenbytes.de/tech/webdav/webfolder-client-list.html "Web Folder Client (MSDAIPP.DLL) Versions and Issues List")  
 More Info [Lists WebDAV clients in Windows (and their bugs)](http://greenbytes.de/tech/webdav/webdav-redirector-list.html "WebDAV Mini-Redirector (MRXDAV.SYS) Versions and Issues List")  