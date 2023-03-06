---
title: 'Description of Windows service wrappers'
date: '2003-09-21T01:48:24+02:00'
status: publish
permalink: /article/winnt-services-wrapper.html
author: Snakefoot
excerpt: 'Description of how Windows services are hosted within the same process.'
type: post
id: 632
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - windows-services
post_format: []
tags:
    - windows-services
---
##### What is a service wrapper ?

 For a service to operate it has to present a certain interface to the operating system, f.ex. so the service can be stopped and started. The implementation of this interface is very similar for many services, so to minimize the size and complexity of the actual service it is placed inside a service wrapper. The service wrapper also saves resources by only using a single proces to have several services running.  
 When having problems with a service wrapper, then it is usually caused by one or more of the services running within the context of the service wrapper.  
##### Which service wrappers exist ?

 Some of the common service wrappers, which can be seen in the Task Manager:
- **Services.exe** : Services Control Manager for system services.
- **Lsass.exe** : Local Security Authority SubSystem for security services. More Info [MS KB308356](http://support.microsoft.com/kb/308356 "Memory Usage by the Lsass.exe Process on Windows 2000-Based and Windows Server 2000-Based Domain Controllers [Q308356]")
- **Svchost.exe** : Service Host for loading dynamic-link libraries (DLL) as a services
- **Dllhost.exe** : DCOM DLL Host Process (Aka. COM Surrogate)supports DLL based COM objects. (Replaces Mtx.exe)
- **Svrany.exe** : Applications as Services Utility. Related [Install an application as a Windows service](/article/winnt-services-srvany.html).
 
 More Info [MS KB263201](http://support.microsoft.com/kb/263201 "Default Processes in Windows 2000 [Q263201]")  
 More Info [MSDN - Componentized Windows Services](http://msdn2.microsoft.com/en-us/library/ms912860.aspx)
 
##### Why does the service wrappers request access to the Internet ?

 When a service inside a service wrapper needs to access the network, then has to go through the service wrapper, so the service wrapper becomes the one trying to get access. Therefore one should be careful before using a firewall to block network access for a service wrapper. Usually one can see what service that wants access, by looking at the port number:
- [DNS Client](/article/winnt-services-dnscache.html) (Port 53)
- [DHCP Client](/article/winnt-services-dhcp.html) (Port 67)
- [Windows Time](/article/winnt-services-w32time.html) (Port 123)
- [SSDP Discovery Service](/article/winnt-services-ssdpsrv.html) (Port 1900/5000)
 
 Note if using a software firewall and gives access for a service wrapper, then it means that all services within the service wrapper is given access, unless specifying a rule where only a certain port number is allowed for the service wrapper.  
  
 Note to see the processes along with the port numbers used:
- **WinXP** (Will show open ports and the process-id they belong to)
  > netstat -ano  
  >   
  >  Note to convert the process-id to a process-name use TList/Tasklist (See below), and if the process is a service wrapper then one can also see the services running within the service wrapper.
- **WinXP SP2** (Will show open ports and the process-name and component they belong to)
  > netstat -b
- **CurrPorts** by [Nirsoft](http://nirsoft.mirrorz.com/) is a GUI version of netstat that works with WinNT/2k/XP
 
 More Info [MS KB832017](http://support.microsoft.com/kb/832017 "Port Requirements for the Microsoft Windows Server System [Q832017]")  
 More Info [MS Reskit: TCP and UDP Port Assignments](http://www.microsoft.com/technet/prodtechnol/windows2000serv/reskit/cnet/cnfc_por_gdqc.mspx "Windows Server 2000 Resource Kit : TCP and UDP Port Assignments")
 
##### How to see the services currently loaded by the wrapper ?

 The Task Manager will only show the wrapper process itself and not the actual services. Instead use this command to see what services are hidding behind the process names:
- Vista: 
  - Open the Task Manager (Hold down the keys CTRL + ALT + ESC) and right-click the service-wrapper proces and select "Go to Service(s)"
- WinXP:
  > Tasklist /SVC
- WinNT4/Win2k (Found on CD in X:\\Support\\Tools):
  > Tlist /S
 
 Note if not into command line tools then try Sysinternals [Process Explorer](http://www.microsoft.com/technet/sysinternals/utilities/ProcessExplorer.mspx)
 
##### Why is Svchost.exe listed several times in the task list ?

 This is because Svchost.exe can load different groups of services, depending of the different user priviledges needed for a certain group or for isolating critical services for increased stability and ease of debugging.  
  
 To see the different groups of which Svchost uses go here with a registry editor (REG\_MULTI\_SZ):
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows NT \\CurrentVersion \\Svchost\]  
>  NetworkService = "..." (Network User)  
>  LocalService = "..." (Local User)  
>  netsvcs = "..." (System User)  
>  rpcss = "RpcSs" (System User, Critical Service)

 Note it is possible to create a new group, and move a service started with Svchost into this group. This can be useful to diagnose which in a group of services is causing unwanted behavior like high CPU / RAM usage.
1. Find the group that contains the service to investigate (ex. netsvcs)
2. Create a new group by adding another REG\_MULTI\_SZ value (ex. netsvcs2) 
  - If there exists a sub-key with the name as the group (ex. netsvcs), then make a copy of the sub-key and give it the new name (ex. netsvcs2)
3. Edit the REG\_MULTI\_SZ for the new group (ex. netsvcs2) and add the service to investigate (ex. wuauserv)
4. Edit the REG\_MULTI\_SZ for the original group (ex. netsvcs) and remove the service (ex. wuauserv)
5. Go to the [registry key for the service](/article/winnt-services-regedit.html) (ex. wuauserv) and change the ImagePath value to reflect the new group (ex. svchost.exe -k netsvcs2)
 
 More Info [MS KB250320](http://support.microsoft.com/kb/250320 "Description of Svchost.exe in Windows 2000 [Q250320]")  
 More Info [MS KB314056](http://support.microsoft.com/kb/314056 "A Description of Svchost.exe in Windows XP [Q314056]")  
##### What could cause a service wrapper to crash ?

 If a single service running within the service wrapper performs a faulty operation, then it is possible for that single service to take down the whole service wrapper along with all other services running within the service wrapper. This can be experienced when open to these exploits: - [Blaster RPC Exploit](/article/winnt-blaster-rpc-exploit.html) (Services.exe / Svchost.exe)
- [Sasser LSA Exploit](/article/winnt-sasser-lsa-exploit.html) (Lsass.exe)
- [Graweg NetApi32 Exploit](/article/winnt-graweg-netapi32-exploit.html) (Services.exe / Svchost.exe)

##### Why is the service wrapper using 100 percent of the CPU ?

 This is not normal behavior and is usually caused by a malfunctioning service running inside the service wrapper. To diagnose what service is causing the trouble:
- Look in the Event Log for error messages, and if error messages are present then use them as starting point.
- If no error messages then one can try to use the Windows Task Manager to find the service-wrapper causing the trouble, and then use the technique described above for discovering what services resides inside the service-wrapper. 
  - Some trojans, spyware, malware software tries to hide themselves by using executable name of a service wrapper. Make sure the system is not infected.
- If no clear evidence of what service is causing the trouble, try to close down each service in the service wrapper one by one and see when the problem goes away (be careful with critical services). Another way is to move each service out in its own service wrapper by using the method described above.
- These services are usually causing trouble for people: 
  - [System Restore Service](/article/winnt-services-srservice.html) can fail when trying to create a restore point, which leads to high CPU usage. The solution is usually to clear all restore points.
  - [Automatic Updates](/article/winnt-services-wuauserv.html) can fail when trying to contact Microsoft to see if any new updates are available. More Info [Repair Automatic Updates](/article/winnt-automatic-updates-repair.html).