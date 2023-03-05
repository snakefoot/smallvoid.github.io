---
title: 'Description of Master Browser in the Microsoft Network'
date: '2003-02-21T22:23:14+01:00'
status: publish
permalink: /article/windows-master-browser.html
author: Snakefoot
excerpt: 'The use of the master browser in the microsoft network, and how it is elected.'
type: post
id: 204
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - master-browser
    - microsoft-network
    - windows-domain
post_format: []
tags:
    - 'master-browser,microsoft-network,windows-domain'
---
The computers listed in the Network Neighborhood comes from the Browser-list maintained by the computer being Master Browser. A computer can become Master Browser through an election where the computer with the highest priority is elected.  
  
 There are different roles for computers participating in a Microsoft Network :

- **Non-Browser:** Cannot participate in the election or maintain a Browser-list. Reports to the Master Browser with 12 min. intervals, and presumed dead by the Master Browser if it hasn't reported in 3 intervals.
- **Potential Browser:** Able to be Master Browser if elected and can be chosen as Backup Browser by the Master Browser. Reports back like the Non-Browser and if the Master Browser disappears it can start an election.
- **Backup Browser:** Elected by the Master Browser to mirror the Browser-list. Every 15 min. the Backup Browser requests an updated Browser-List from the Master Browser. There is a Backup browser elected for every 32 computer.
- **Master Browser:** Responsible for maintaining the Browser-list by adding and removing computers for a single subnet.
- **Domain Master Browser:** (Primary Domain Controller) Responsible to maintain the Browser-list in a Domain. It collects Browser-lists from all Master Browsers and distributes the entire Browser-list to all Master Browsers in the domain.
 
 A computer's priority in the election depends on the operating system:
- Windows For Workgroups or Windows 9x : 0x01000000
- Windows 2000, NT4, XP Prof. : 0x10000000
- Windows 2000, NT4 Srv. : 0x20000000
 
 A computer's priority in the election depends on the configuration:
- Primary Domain Controller(PDC) : 0x00000080
- WINS System : 0x00000020
- IsDomainMaster = Yes : 0x00000008
- Running Master Browser: 0x00000004
- MaintainServerList = Yes : 0x00000002
- Running Backup Browser: 0x00000001
 
 Note if a computer is frequently turned On/Off or having few resources available(Mobile Computer), then one should configure it as Non-Browser so it won't start unnecessary elections.  
  
 Note if having a LAN where one computer is configured to belong on a different subnet than the default or if the computer for some other reason cannot see the current master browser (Usually the Primary Domain Controller). Then this computer will constantly issue Master Browser election, because it cannot find a Master Browser. This can lead to a blank Browser-list for all the computers in the LAN.  
  
 Note if a router is used to connect two LANs and it is configured wrong, then the two LANs will affect each other in the Master Browser election. This can lead to a blank Browser-list for all computers in both LANs.  
  
 Note if a computer is multihomed (several network adapters connected to the same network), then it will not function properly as Master/Backup/Domain Browser, and should not participate in the election.  
  
 Configure which computer becomes Master Browser :
- [Control Master Browser in Windows 9x/Me](/article/win9x-master-browser.html)
- [Control Master Browser in Windows NT/2k/Xp](/article/winnt-master-browser.html)
- [Linux &amp; Samba](http://samba.linuxbe.org/) uses [/etc/smb.conf](http://samba.org/samba/docs/man/manpages-3/smb.conf.5.html)> \[global\]  
  >  workgroup = MYGROUP  
  >  netbiosname = myhostname  
  >  encrypt passwords = yes  
  >   
  >  #Whether to become master browser (yes, no)  
  >  local master = no  
  >   
  >  #Whether to become master browser in domain (auto, yes, no)  
  >  domain master = no  
  >   
  >  #Whether to have higher priority in election (auto, yes, no)  
  >  preferred master = no  
  >   
  >  #Whether to have higher priority compared to other OS (0-255)  
  >  #default 20, Win95=1, WinNT Pro=17, WinNT Srv=33  
  >  os level = 0
 
 More Info [Microsoft Windows NT Browser](http://www.microsoft.com/ntserver/techresources/commnet/browser/ntbrowser.asp)  
 More Info [MS KB102878](http://support.microsoft.com/kb/102878 "Information on Browser Operation [Q102878]")  
 More Info [MS KB188001](http://support.microsoft.com/kb/188001 "Description of the Microsoft Computer Browser Service [Q188001]")  
 More Info [MS KB188305](http://support.microsoft.com/kb/188305 "Troubleshooting the Microsoft Computer Browser Service [Q188305]")  
 More Info [MS KB191611](http://support.microsoft.com/kb/191611 "Symptoms of Multihomed Browsers [Q191611]")  