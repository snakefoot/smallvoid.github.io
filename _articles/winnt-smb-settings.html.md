---
title: 'Optimizing the file sharing network to handle more traffic'
date: '2001-01-01T23:48:14+01:00'
permalink: /article/winnt-smb-settings.html
author: Snakefoot
excerpt: 'Prepare the file servers to handle a higher loads and allow the clients to make more requests.'
type: post
id: 440
categories:
    - windows-2003_file-sharing
    - windows-nt4_file-sharing
    - windows-xp_file-sharing
    - windows-2000_file-sharing
tags:
    - microsoft-network
    - network-performance
---
MaxCmds specifies the maximum outstanding network requests for the client to the server, which is used when negotiating a Server Message Block (SMB) connection with a server.

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanWorkstation \\Parameters\]  
>  MaxCmds = 100 (Range 0 - 255(NT4) - 65535(Win2k). Default is 50 (NT4 = 15))

 MaxMpxCt specifies the maximum outstanding network requests for the server per client, which is used when negotiating a Server Message Block (SMB) connection with a client. Note if the value is set beyond 125 older Windows 9x client will fail to negotiate.
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  MaxMpxCt = 100 (The range is 0 - 100(NT4) - 65535(Win2k) and the default is 50)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+232890+Q232890" rel="nofollow" title="Windows 98 Client Unable to Connect to Windows NT Share [Q232890]">MS KB232890</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+926646+Q926646" rel="nofollow" title="You cannot increase the limit concurrent SMB command in the Windows XP Professional Server service">MS KB926646</a> (XP is limited to 10 without hotfix).

 MaxWorkItems specifies how many active requests the server will handle at once (Besides those outstanding) before it starts to reject or throttle incoming requests. Note the default value is calculated and is based upon the total amount of RAM and CPU's, and it should only be changed on servers where the calculated value is not enough to handle all client requests (The value should at least be 4 times the value of MaxMpxCt).
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  MaxWorkItems = 512 (The range is 0 - 64(Prof.) - 65535 (Srv.))

 The MaxFreeConnections and MinFreeConnections controls how many connection objects, which are preallocated. The preallocation requires extra memory, but enables faster handling of network requests.
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  MinFreeConnections = 4 (2 = Minimize, 2 = Balance, 4 = Sharing, 4 = Network Applications)  
>  MaxFreeConnections = 8 (2 = Minimize, 4 = Balance, 8 = Sharing, 8 = Network Applications)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+245080+Q245080" rel="nofollow" title="Receiving Multiple Instances of Event ID 2022 [Q245080]">MS KB245080</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+909262+Q909262" rel="nofollow" title="Description of the changes to the mechanism that Windows Server 2003 uses to allocate resources [Q909262]">MS KB909262</a>

 The MaxThreads specifies how many threads is allowed to run at once, each thread allows one outstanding operation. By increasing this you can increase the amount of simultaneous work. Each extra execution thread will take 1 Kbyte of additional nonpaged pool memory.
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanWorkstation \\Parameters\]  
>  MaxThreads = 30 (The range is 0-255 and the default is 17)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+115522+Q115522" rel="nofollow" title="Limits on Overlapped Pipe Operations [Q115522]">MS KB115522</a>

 The MaxCollectionCount specifies how much data there can be stored in a named pipe before a write operation is triggered. Increase this value can increase performance for applications which uses named pipes, as it will lower the amount of write operations.
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanWorkstation \\Parameters\]  
>  MaxCollectionCount = 32 (The range is 0-65535 and the default is 16)

 Related [Configure the file server request buffer size](/article/winnt-smb-request-buffer.html)  
 Related [Configure the memory usage of the Server service](/article/winnt-server-config.html)  
  
 More Info <a href="https://www.bing.com/search?q=KB+102967+Q102967" rel="nofollow" title="REG: Server Service Entries, PART 1 [Q102967]">MS KB102967</a>  
 More Info <a href="https://www.bing.com/search?q=KB+221790+Q221790" rel="nofollow" title="IIS Runs Out of Work Items and Causes RPC Failures When Connecting to a Remote UNC Path [Q221790]">MS KB221790</a>  
 More Info <a href="https://www.bing.com/search?q=KB+232476+Q232476" rel="nofollow" title="Terminal Server Client Connections and Logon Limited by MaxWorkItem and MaxMpxCt Values [Q232476]">MS KB232476</a>  
 More Info <a href="https://www.bing.com/search?q=KB+271148+Q271148" rel="nofollow" title="MaxMpxCt and MaxCmds Limits in Windows 2000 [Q271148]">MS KB271148</a>  
 More Info <a href="https://www.bing.com/search?q=KB+317249+Q317249" rel="nofollow" title="How to Troubleshoot Event ID 2021 and Event ID 2022 [Q317249]">MS KB317249</a>  
  
 Credits [regedit.com](http://registry.winguides.com/display.php/56/)