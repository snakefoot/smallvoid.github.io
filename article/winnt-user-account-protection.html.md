---
title: 'Configure User Account Protection'
date: '2005-09-25T22:11:49+02:00'
status: publish
permalink: /article/winnt-user-account-protection.html
author: Snakefoot
excerpt: 'User Account Control (UAC) makes sure that daily tasks are not performed with administrator privileges.'
type: post
id: 455
category:
    - 'User Security'
tag:
    - user-account-control
post_format: []
tags:
    - user-account-control
---
Many users give themselves Administrator rights even for daily tasks, so if attacked by malicious software then it will also get Administrator rights.  
 User Account Protection (UAP) is an attempt to solve this problem, by introducing two modes:

- **Admin Approval Mode**, when logged in as local administrators, then one has to give consent to allow an application to perform administrative tasks.
- **Standard User Mode**, when logged in as standard user, then one has to provide credentials for administrator account to allow an application to perform administrative tasks.
 
 When UAP is enabled, then the desktop (Explorer.exe) is launched with Standard User priviledges (Aka. secure desktop), and all application launched from the desktop inherits the same priviledges. Only through the [Application Information Service (AIS)](/article/winnt-services-appinfo.html) can an application can be given an administrator token through consent by the user.  
  
##### Application Virtualization

 UAC provides virtualization to handle all legacy applications that are not used to be executed with standard user priviledges. When a legacy application tries to write to the Program Files directory or the [HKEY\_LOCAL\_MACHINE](http://msdn2.microsoft.com/en-us/library/aa965884.aspx), then it is redirected to a local user folder:
- C:\\Users\\username\\Appdata\\Local\\VirtualStore
- HKEY\_CURRENT\_USER\\Software\\Classes\\VirtualStore\\MACHINE\\SOFTWARE
 
 If an application marks itself as a Vista ready with a [requestedExecutionLevel manifest](http://msdn.microsoft.com/en-us/library/bb756929.aspx), then it will not be virtualized but will be denied access instead.  
  
 Applications are only virtualized when UAC is enabled, so disabling UAC also disables the protection of virtualization. More Info [MS KB927387](http://support.microsoft.com/kb/927387 "Common file and registry virtualization issues in Windows Vista")  
  
##### User Confirmation Dialog

 When requesting for confirmation through consent or credentials, then UAP switches to secure desktop mode (black dimmed background) where only processes with SYSTEM privileges can interact. This prevents applications from messing with the consent popup dialog (ex. pressing the Continue-button for the user, or intercept the password).  
  
 To configure whether UAP should be enabled or not:
1. Press **Start** and execute the following command:
   > control userpasswords
2. Click "Turn User Account Control on or off" and uncheck "Use User Account Control (UAC) to help protect your computer"  
    
   Should be reflected in this registry key:
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\System\]  
  >  EnableLUA = 1 (Default = 1; Disabled = 0)  
  >   
  >  Note when disabled [Security Center](/article/winnt-services-wscsvc.html) will display a [balloon message](/article/winnt-balloon-tip.html#SECURITY_CENTER) at every boot warning that User Account Control is turned off.
 
 To configure UAP to request credentials instead of just a consent dialog:
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the tree-view go to "Local Policies" -&gt; "Security Option"
3. Modify the option "User Account Protection: Behavior of the elevation prompt for administrators" 
  - No Prompt (0)
  - **Prompt for credentials** (2)
  - Prompt for consent (1)
   
   This should be reflected in this registry key:
   > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\System\]  
   >  ConsentPromptBehaviorAdmin = 2 (Default = 1; Disabled = 0)
 
 To configure whether UAP should switch to secure desktop when asking for consent or credentials:
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the tree-view go to "Local Policies" -&gt; "Security Option"
3. Modify the option "User Account Control: Switch to the secure desktop when prompting for elevation"  
    
   Should be reflected in this registry key:
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\System\]  
  >  PromptOnSecureDesktop = 1 (Default = 1; Disabled = 0)
 
<a name="ELEVATED"></a>
##### Start application with Administrator privileges

 By default when launching application from the desktop, they will not be given Administrator rights. There are different ways to launch an application with Administrator privileges:
- Right-click the shortcut to the application and choose the "Run as Administrator" option.
- Create a shortcut to the application, and change the properties for the shortcut link. On the "Shortcut"-tab there will be an "Advanced"-button that will allow one to set "Run as Administrator" as default.
- Press the Start Orb and ex. type "cmd", but instead of pressing ENTER, press CTRL+SHIFT+ENTER and it will be launched as an **Elevated Command Prompt** with Administrative rights.
- Use [RunAs](/article/winnt-services-seclogon.html) to launch as Administrator (Will have to supply the password), consider the option **/noprofile** for faster load:
  > C:\\Windows\\System32\\runas.exe /user:administrator "cmd %L"
- Extend the context menu for the filetype (file-extension) with the option to open the file with administrator rights (Ex. start msi-installer with administrator rights):
  > REGEDIT4  
  >   
  >  \[HKEY\_CLASSES\_ROOT\\Msi.Package\\shell\\runas\]  
  >  @="Install &amp;as..."  
  >   
  >  \[HKEY\_CLASSES\_ROOT\\Msi.Package\\shell\\runas\\command\]  
  >  @="msiexec /i "%1""
 
 Related [Run elevated using scheduled task to avoid UAC prompt](/article/winnt-uac-scheduled-task.html)  
 Related [Script Elevation PowerToys for Windows Vista](http://www.microsoft.com/technet/technetmag/issues/2007/06/UtilitySpotlight/default.aspx)  
  
 Credits [TweakVista.com](http://www.tweakvista.com/)